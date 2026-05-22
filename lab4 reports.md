# Lab 实验报告


## 一、思考题

## Thinking 4.1

### 1. 内核在保存现场的时候是如何避免破坏通用寄存器的？

- 使用 `k0`/`k1` 这两个**内核专用寄存器**（用户态不会用，异常时也不会保存）
- 先用 `k0`/`k1` 暂存 CP0 寄存器的值，再把 `k0`/`k1` 存到栈上
- 这样就不会破坏任何通用寄存器（`$0-$31`）的值

**代码：** `SAVE_ALL` 宏中 `mfc0 k0, CP0_STATUS` → `sw k0, TF_STATUS(sp)`

---
关于`TrapFrame`
### 2. 系统陷入内核调用后可以直接从当时的 `$a0`-`$a3` 参数寄存器中得到用户调用 msyscall 留下的信息吗？

**不能！**
- 陷入内核后，**$a0-$a3 的值已经被保存到 Trapframe 里了**
- 内核需要从 `tf->regs[4]` ~ `tf->regs[7]` 读取，而不是直接读寄存器



### 3. 我们是怎么做到让 sys 开头的函数"认为"我们提供了和用户调用 msyscall 时同样的参数的？

- `do_syscall` 从 Trapframe 把 `a0`（syscall号）、`a1-a3`（参数）提取出来
- 再从用户栈 `tf->regs[29] + 16/+20` 取出第4、5个参数
- 把这些参数按顺序传给 `sys_xxx` 函数，就好像用户直接调用一样
---

### 4. 内核处理系统调用的过程对 Trapframe 做了哪些更改？这种修改对应的用户态的变化是什么？

- `tf->cp0_epc += 4`：跳过 syscall 指令本身，避免死循环
- `tf->regs[2] = 返回值`：把系统调用返回值存入 $v0
- 用户态 eret 返回后，PC 就是 syscall 下一条指令，$v0 就是返回值

---

## Thinking 4.2

### 为什么 envid2env 中需要判断 `e->env_id != envid` 的情况？如果没有这步判断会发生什么情况？


- **原因：** 同一个数组槽位可能被复用。进程销毁后槽位被回收，新进程可能分配到同一个槽位（同一个 `e` 地址），但 `env_id` 是不同的。
- **没有这步会：** 拿着旧进程的 envid 去操作新进程，造成权限越界.
---

## Thinking 4.3

### mkenvid() 函数不会返回 0，请结合系统调用和 IPC 部分的实现与 envid2env() 函数的行为进行解释。

- `envid2env` 中约定：**envid = 0 表示当前进程**（`curenv`）
- 如果 `mkenvid()` 可能返回 0，就无法区分"当前进程"和"id=0的那个进程"了
- 所以 mkenvid 从 1 开始递增，保证 0 永远不会被分配，保留为"指代自身"的特殊值

---

## Thinking 4.4

### 关于 fork 函数的两个返回值，下列说法正确的是？

- `sys_exofork` **只在父进程执行一次**
- 内核创建子进程，复制 Trapframe，把父进程 EPC 和 $v0 都复制过去
- 两个进程分别从 eret 返回：
  - 父进程：返回子进程 pid
  - 子进程：返回 0（因为内核手动设了 `e->env_tf.regs[2] = 0`）
- 所以是**一次调用，两个返回**

---

## Thinking 4.5

### 1. 为什么子进程的 UXSTACK 必须重新分配，而不能共享或设为 COW？

- UXSTACK 是**每个进程私有的异常栈**，用来处理 TLB Mod 等异常
- 如果共享，父子进程同时发生异常时会互相覆盖栈内容
- 如果设为 COW，异常发生时栈访问触发 TLB Mod，又要往栈上写，**死循环**

---

### 2. 为什么不应对 UVPT/VPT/VPD 等自映射区域调用 duppage？如果误处理，可能引发哪些不一致或错误行为？


- UVPT/VPT/VPD 是**自映射区域**，由硬件根据页目录基址自动映射，不是实际的物理页
- `duppage` 对普通物理页做 COW，但自映射区域"映射的是页表本身"，父子进程有独立的页目录
- 误处理会导致：子进程看到的页表不是自己的，修改 vpt 会意外修改父进程的页表，内存隔离失效

---

## Thinking 4.6

### 1. vpt 和 vpd 的作用是什么？怎样使用它们？


- `vpt`（Virtual Page Table）：把整个页表当一个数组来访问，`vpt[VPN]` 就是对应虚拟页的 PTE
- `vpd`（Virtual Page Directory）：访问页目录，`vpd[PDX(va)]` 就是页目录项
- 使用：直接当指针解引用，比如 `pte_t pte = vpt[va >> PGSHIFT]`

---

### 2. 从实现的角度谈一下为什么进程能够通过这种方式来存取自身的页表？


- 页目录的**最后一项指向页目录本身**（自映射）
- 这样 `UVPT + 4*VPN` 这个虚拟地址，经过 MMU 两级翻译后，正好指向页表中对应的 PTE
- 硬件帮我们完成了地址翻译，软件就可以像访问普通内存一样访问页表

---

### 3. 它们是如何体现自映射设计的？进程能够通过这种方式来修改自己的页表项吗？

- 体现：页目录最后一项 PDX(UVPT) = 页目录的物理地址 | 权限位，形成"自己指向自己"的环
- **用户态不能修改**：因为这些页表页的 PTE 没有 `PTE_D`（写权限），用户态写会触发 TLB Mod
- 只能通过 `sys_mem_map` 等系统调用让内核修改

---

## Thinking 4.7

### 1. 什么时候会出现"异常重入"？


- 当异常处理程序本身又触发异常时。比如：
  1. 用户态写 COW 页，触发 TLB Mod 异常
  2. 内核把 Trapframe 复制到 UXSTACK 上返回用户态处理
  3. 用户态异常处理函数执行时，如果触发了另一个异常（比如缺页）
- 这就需要第二个异常的现场不覆盖第一个异常的现场

---

### 2. 内核为什么需要将异常的现场 Trapframe 复制到用户空间？


- 异常处理逻辑是**用户态实现**的（`cow_entry`），不是内核态
- 用户态处理函数需要知道：哪个地址触发了异常、当时各寄存器的值、EPC 是多少
- 复制到 UXSTACK 上，用户态函数就能直接用指针访问 Trapframe 了

---

## Thinking 4.8

### 在用户态处理页写入异常，相比于在内核态处理有什么优势？


1. **微内核设计思想**：把策略（什么时候复制、怎么复制）放到用户态，内核只提供机制
2. **减少内核代码复杂度**：内核不用处理各种复杂的页错误情况
3. **更灵活**：不同进程可以注册不同的异常处理函数
4. **安全性**：异常处理在用户态运行，崩溃了只会影响当前进程，不会整个系统挂掉

---

## Thinking 4.9

### 为什么在设置写时复制保护机制之前，需通过 syscall_set_tlb_mod_entry 设置父进程页写入异常处理函数？若在写时复制保护机制完成之后再设置会怎样？


- **原因：** 设置 COW 保护后，任何写操作都会立即触发 TLB Mod 异常，如果先设置 COW 再注册处理函数，中间有一个**窗口**，此时异常触发了但没有处理函数，直接 panic
- **之后设置会：** 出现竞态条件！`duppage` 取消了 PTE_D → 还没来得及 `sys_set_tlb_mod_entry` → 父进程写了那个页 → 触发 TLB Mod → 处理函数为空 → `panic("TLB Mod but no user handler registered")`


### COW写时复制异常流程
![2](assets/image-12.png)
---

## 二、难点分析与实验体会
### 中断处理流程
```
【外部中断/异常】
        |
【异常处理入口】 -- Entry.S 1 SAVE_ALL（内核态进入-sp生长、用户态进入，Trapframe放在KstackTop部分）
        |
genex.S 分配具体的handle函数【分发】
        |
do_tlb_refill() - RESTORE_ALL(ret_from_exception) 把trapframe恢复到寄存器中，【不切换进程，$sp不动，返回到异常指令PC】

or handle_int  --- schedule() --- env_run.. ---  RESTORE_ALL(ret_from_exception)【切换进程，$sp切换，然后恢复】

```
### 1. 核心难点（如命令使用/逻辑实现等）
分析与解决思路

### 2. 实验收获/技巧总结
1. C语言补充，枚举
```C
//一个枚举类型，可以取出多个函数
void *syscall_table[MAX_SYSNO] = {
    [SYS_putchar] = sys_putchar,
    [SYS_print_cons] = sys_print_cons,
    ....
};
```
2. checkperm 除了IPC相关的syscall，都需要设为1，只能用在自己或者自己的子进程上。
3. 每一个进程的虚拟地址和其envid绑定

syscall：
进程相关：分配页表，映射，取消映射

1. 我们在lab3 把大量的内容暴露给了用户态（微内核），例如PCB 
2. 不可重入异常：直接将trapframe 保存在KSTACK栈顶。

**用户程序**
入口：定义在Linker script当中的`_start()`，在用户态中的`entry.S`汇编入口
+ 虽然时写的时候是从`main()`，但是实际上经历了大量的预处理。
+ int main(int argc, char **argv) 
```S
.text
EXPORT(_start)
	lw      a0, 0(sp) # int argc
	lw      a1, 4(sp) # char **argv
	jal     libmain
```
+ 例如预处理程序 libos.c 创建进程 销毁进程
```C
extern int main(int, char **);

void libmain(int argc, char **argv) {
	// set env to point at our env structure in envs[].
	env = &envs[ENVX(syscall_getenvid())];

	// call user main routine
	main(argc, argv);

	// exit gracefully
	exit();
}
```
### 3. 实验注意事项
操作避坑/效率提升等注意点

---

## 三、原创说明
本报告基于实验指导书和代码实现完成, 以及助教讲解视频
