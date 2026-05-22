# 北京航空航天大学

# 2021-2022 学年第二学期期末

《操作系统》

考试试卷

班级 学号

姓名 成绩

## 登分表

<table><tr><td rowspan=1 colspan=1>题号</td><td rowspan=1 colspan=1>得分</td><td rowspan=1 colspan=1>阅卷签名</td></tr><tr><td rowspan=1 colspan=1>二</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>三</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>三</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>四</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>五</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>六</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>七</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>八</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>总分</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr></table>

注意事项：

1、请在封面、每页试卷和答卷顶部方格中都填上学号，请工整填写；

2、试卷不要拆卸，以免散落丢失；

3、所有答案写在试卷后的空白答题纸上（包括判断、选择题），写清题号；

2022 年 06 月 18 日

<!-- image-->

## 一、 判断题（本题共 10 分，每小题 1 分）

1. 一个进程被唤醒意味着该进程重新占有了CPU。（ ）

2. I/O 通道控制方式不需要任何 CPU 干预。（ ）

3. 分页、请求分页存储管理技术的逻辑地址由页号p和页内地址d组成，因此是一个二维地址。（ ）

4. 在作业调度时, 采用最高响应比优先的作业调度算法可以得到最短的作业平均周转时间。（ ）

5. 树型目录结构能够解决文件重名问题。（ ）

6. 批处理系统的主要优点是系统的吞吐量大、资源利用率高、系统的切换开销较小。（ ）

7. 在多对一线程模型中，同一个进程内的两个线程，不能同时陷入内核请求系统调用服务。（ ）

8. 文件系统中的源程序文件是有结构的记录式文件。（ ）

9. 操作系统在执行系统调用时可以被中断。（ ）

10.在页式虚拟存储系统中，使用fork创建的子进程总是和父进程共享相同的代码和数据页，因此子进程和父进程之间可通过全局变量实现数据传递。（ ）

## 二、 单项选择题 (本题共 20 分，每小题 2 分)

1. 批处理系统的主要缺点是 。A.CPU 的利用率不高 B.失去了交互性C.不具备并行性 D.以上都不是

2. 以下说法正确的是 。A. 两个不同进程对应的页表中可能包含内容相同的页表项；B. 虚拟地址空间总是大于物理地址空间；C. 在页式内存管理下，页面尺寸越小越有利于消除外碎片，提高内存使用效率；D.在段式内存管理下，不同分段尺寸大小可以不同，从而可以消除外碎片，提高内 D. 在段式内存管理下，不同分段尺寸大小可以不同，从而可以消除外碎片，提高内存使用效率。

3. 下列哪些属于反置页表的优点？ A. 查找页表项的速度快

<table><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table>

B. 缺页处理速度快C. 便于进程之间共享数据D. 页表占用的内存空间小

4. 用户程序代码被操作系统加载到内存中的过程称为 。A. 编译； B. 链接； C. 装载； D. 置换。

5. 关于多级页表，下列说法不正确的是： 0A. 能够减少页表占用内存的大小B. 级数越多，平均访问内存的时间越长C. 有效的页表项中都会存储页框号D. 使用二级页表的平均访存性能优于一级页表

6. 以下说法正确的是： 0A. 进程上下文切换过程一定会陷入内核B. 陷入内核一定会导致进程切换C. 正在执行的程序不可以主动放弃 CPUD. 系统调用一定会导致进程上下文切换

7. 下列算法中可用于进程调度和磁盘调度的是 A. FCFS B. SSTF C. 时间片轮转 D. SJF

8. 关于IPC，不正确的是A. 消息传递比信号的信息承载量要大B. 共享内存是最快的 IPC 形式C. 套接字不仅可用于不同机器之间的进程通讯，也可用于本机的两进程通讯D. 共享内存在效率和安全性上都要优于消息传递

9．从磁盘将1个数据块传送到缓冲区所用时间为80us，将缓冲区中数据传送到用户区所用时间为40us，CPU处理一个数据块所用时间为30us。如果有很多数据块需要处理，采用单缓冲区传送磁盘数据，则处理1个数据块所用平均时间接近 。A．120us B. 110us C. 150us D. 70us

10．设有一个包含多个记录的索引文件，每个记录正好占用一个物理块。如果每一个物理块可以存放10个索引表的条目，在建立索引结构时，一个物理块需要对应一个索引表的条目，每级索引至少占用一个物理块。则：

A．为保存包含 1001 个记录的文件，至少应该建立 3 级索引；

B．保存包含1000个记录的文件，需要至少111个索引块；

C．保存包含 1000 个记录的文件，采用 4 级索引比采用 3 级索引需要多用 1 个索引块；

D．采用 4 级索引最多可以存储 9999 个记录。

## 三、 填空题（本题共 10 分，每个空 2 分）

1. 用户进程通过 请求操作系统执行需要更高权限的操作。

2. 某个程序运行时依次访问的内存页面的页号为：1, 2, 3, 4, 5, 3, 4, 1, 6, 7, 8, 7, 8, 9,7, 8, 9, 5, 4, 5, 4, 2。采用LRU 算法进行页面置换，共为该程序分配了5个页框，如果初始时这5个页框为空，则会产生_ 次缺页中断。

3. 在一个纯分页系统中，采用二级页表，一条访存指令成功执行，最多会产生次实际访存操作（假设此过程中操作系统相关代码都已在Cache中，不涉及访存）。

4. 操作系统中虚拟存储机制有效的基础是程序访存的 _原理。

5. 以下程序编译运行后，存储空间分配在data段上的变量有 （多个变量名之间英文半角逗号隔开，不要留空格）。

```c
int a = 5;
static int b = 1;
int main() {
int c;
static int d;
printf("a=%d, b=%d, c=%d, d=%d\n", a, b, c, d);
}
```

## 四、 死锁问题 (本题共 10 分，每小题 5 分)

5 条章鱼围坐一桌，每条章鱼有 8 只手（腕足）。章鱼不断在进餐和思考状态间切换。思考时章鱼不断尝试抓取桌上的筷子，每只手最多只能抓取1根筷子。每根筷子同时最多只能被一只章鱼手抓取。筷子集中堆放在桌子中央，即任何章鱼都可以抓取桌上的任何筷子，没有位置限制。章鱼抓到 8 根筷子就开始进餐，进餐后将 8 根筷子放回桌上。章鱼抓取到筷子的手在完成进餐前不会将筷子放回桌上。

（1）如果筷子都一样，则至少需要多少根筷子才能保证不出现死锁？说明理由。

（2）如果筷子分为红、绿两种颜色。每条章鱼必须拿到 4 红、4 绿筷子才能进餐，其余条件不变。当前章鱼抓取筷子情况如表1：

表 1
<table><tr><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1>抓到红色筷子数量</td><td rowspan=1 colspan=1>抓到绿色筷子数量</td></tr><tr><td rowspan=1 colspan=1>章鱼A</td><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>1</td></tr><tr><td rowspan=1 colspan=1>章鱼B</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>2</td></tr><tr><td rowspan=1 colspan=1>章鱼C</td><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>2</td></tr><tr><td rowspan=1 colspan=1>章鱼D</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>1</td></tr><tr><td rowspan=1 colspan=1>章鱼E</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>3</td></tr></table>

桌子上还剩 2 红、2 绿筷子，此时，章鱼 D 尝试抓取 1 红、1 绿筷子，为了避免发生死锁，判断是否能够允许章鱼D的这次抓取？说明理由。

## 五、 内存管理（本题共 15分，第 1小题 4分，第2小题 6分，第 3小题3分，第 4小题 2 分）

设一个机器有 38 位逻辑地址和 32 位物理地址，采用二级页表实现地址映射，每页大小为16KB，每个页表项占4字节。请问:

（1） 逻辑地址空间一共有多少字节？物理地址空间一共有多少字节？

（2） 第一级页表分配多少位？第二级页表分配多少位？并解释原因。

（3） 假 设 第 一 级 页 表 的 起 始 物 理 地 址 为 0x0000A000， 请 给 出 逻 辑 地 址0x123456789A对应的第一级页表项的物理地址。

（4） 如果从逻辑地址 0x0004000000 映射整个页表，请给出第一级页表的逻辑地址。（提示：考虑自映射，第一级页表相当于页目录）

## 六、 作业调度（本题共 10 分）

一个作业调度系统的作业接收情况如表 2。假设系统同时只能执行 1 个作业，每个刚到达的作业在其到达时刻就可以开始运行。请问采用 FCFS 算法和短作业优先算法（不抢占）的作业平均周转时间分别是多少？

表 2
<table><tr><td rowspan=1 colspan=1>作业编号</td><td rowspan=1 colspan=1>作业到达时刻（秒）</td><td rowspan=1 colspan=1>作业执行时间（秒）</td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>0時</td><td rowspan=1 colspan=1>5號</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>8</td></tr></table>

<table><tr><td>学号</td></tr></table>

<!-- image-->

<table><tr><td rowspan=1 colspan=1>3號</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>3</td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>10</td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1>4</td></tr></table>

## 七、 进程同步与互斥（本题共 15 分）

在新冠疫情期间，某公园实行限流访问，规定每天最多允许N个人购票入园。公园的在线售票系统提供了查询余票和在线购票功能，查询者 Q 和购票者 B 分别对余票数量进行读操作和写操作。为了简化问题，假定每次只能购买一张票。请基于 PV 操作设计一个算法，实现多个 Q 和 B 对余票数量的并发访问。要求：（1）Q 和 B 按照到达顺序对余票数量进行访问；（2）当多个Q连续到达时，应允许他们并发读取余票数量；（3）当余票为0时，不允许B 执行写操作。

## 八、 文件系统（本题共 10分，每小题 5分）

某磁盘的平均寻道时间是 6ms，旋转速度为 7500rpm（转/分钟），每磁道可存储1048576（即 1024\*1024）字节。该磁盘上文件系统的数据块大小是 4KB，文件的平均大小是 10KB，且文件控制块全部内容直接存储在目录项中。

（1） 若不考虑读取文件控制块的时间，从该磁盘中读取一个文件的平均时间约为多少ms？

（2） 假设只有根目录内容已经读入内存，且每级目录的目录项都位于一个数据块中，读取一个 102KB 的文件/tmp/test/helloworld.c 需要访问磁盘几次？