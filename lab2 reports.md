# Lab2 实验报告


## 一、思考题
### 1. CPU发出地址
（1）编写的C程序中，指针变量存储的地址为**虚拟地址**
（2）MIPS 汇编程序中 lw 和 sw 指令使用的地址也是**虚拟地址**

理解：**只要你在写用户程序，你看到的所有地址都是虚拟地址。物理地址你永远见不到。**

### 2. 知识点2
具体操作/输出/结论

### 3. Page_list的结构与宏的使用
选项C
```C
struct Page_list{
    struct {
        struct{
            struct Page* le_next;
            struct Page** le_prev;
        } pp_link;
        u_short pp_ref;
    }* lh_first;
};
```
因此 我如果想取出le_prev
```C
struct Page_list* p
p -> pp_link.le_prev
```
我如果想要遍历空闲页表
```C
for(struct Page *p = page_free_list->lh_first; p != NULL; p = p->pp_link.le_next);
```
其实就是`LIST_FOREACH(struct Page *p, page_free_list, pp_link)`

---

## 二、难点分析与实验体会
### 1. 核心难点（如命令使用/逻辑实现等）


#### 内存分布
kuseg - 最大，需要经过TLB/页表翻译
kseg0 - 不需要经过页表翻译，直接减去0x80000000得到物理地址
+ 所以想直接访问物理地址，只需要加上0x80000000 转化为逻辑地址的kseg0段，再由CPU操作访问即可。

+ `struct Page*`  物理页面首地址 kseg0段的va虚拟地址
三者转换
- 当我要对地址具体内容修改时，我应当对kseg0段的va虚拟地址进行修改，而非物理地址！！
  
访问指定页表的内存`(pp - pages) * PAGE_SIZE + 0x80000000`
考试时只需要使用`page2kva(pp);`即可
#### 内核的内存
freemem之前包含 .data .text .bss 以及所有struct page 结构体，每一个结构体指向物理内存的一页（双向映射）
+ 这些内核的部分不能被分配，所以应当标记为已使用

### 2. 实验收获/技巧总结
具体总结内容
**1. 链表操作宏定义化**。

#### 2.双向链表的小巧思
前驱指针使用双重指针
```C
#define LIST_ENTRY(type)                                                         
	struct {                                                                                   
		struct type *le_next;  /* next element */                                          
		struct type **le_prev; /* address of previous next element */ //解引用得到上一页的le_next指针，这样的话就不需要判断指针为空，（因为指针变量一定有地址）                     
	}
```
#### 3.多参数返回
使用指针传参，
```C
int page_alloc(struct Page **new) {
	struct Page *pp;
    ...
	*new = pp;
	return 0;
}
```

#### 4. 转换


### 3. 实验注意事项
操作避坑/效率提升等注意点

---

## 三、原创说明
参考资料/原创声明等
                             