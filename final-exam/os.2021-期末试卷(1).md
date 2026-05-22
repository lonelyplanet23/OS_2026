# 北京航空航天大学

# 2020-2021 学年第二学期期末

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

2021 年 06 月 10 日

## 一、 判断题（本题共 10分，每题 1分）

<!-- image-->

1. 中断方式的数据传送是在中断处理时由CPU 控制完成的；而在DMA方式下，数据传送过程不经过CPU，是在DMA控制器的控制下完成的。（ ）

2. 管道机制中的数据只存在于内存中。（ ）

3. 在一个磁盘上设置多个分区能改善磁盘设备 I/O 性能。（ ）

4. 分页存储管理技术，是用于虚存管理的技术，但也可以用于物理内存管理。（ ）

5. 简单地说，进程是程序的执行过程。因而，进程和程序是一一对应的。（ ）

6. 操作系统中的Spooling技术，实质是将独占设备转换为共享设备的技术。（ ）

7. 将二进制证书转换为文本以便打印是设备无关软件层负责的。（ ）  
8. 一个物理硬盘可以分成多个逻辑硬盘分区进行面向用户文件系统的管理。（ ）  
9. 设备控制器是一块能控制一台或多台外围设备与 CPU 并行工作的硬件。（ ）

10. 在内存管理中，地址空间不能小于物理内存空间。（ ）

## 二、 单项选择题 (本题共 20 分，每小题 2 分)。

1. 下列选项中，不可能在用户态发生的事件是 0A．系统调用 B．外部中断 C．进程切换 D．缺页

2. 在支持多线程的系统中，进程P 创建的若干个线程不能共享的是 。A．进程 P 的代码段 B. 进程P 中打开的文件C. 进程P 的全局变量 D. 进程P 中某线程的栈指针

3. 若一个用户进程通过read系统调用读取一个磁盘文件中的数据，则下列关于此过程的叙述中，正确的是 。Ⅰ、若该文件的数据不在内存，则该进程进入阻塞状态Ⅱ、请求 read 系统调用会使 CPU 从用户态切换到核心态Ⅲ、 read 系统调用的参数应包含文件的名称A. 仅Ⅰ、Ⅱ B. 仅Ⅰ、Ⅲ C. 仅Ⅱ、Ⅲ D. Ⅰ、Ⅱ和Ⅲ

4. 假设磁头当前位于第105道，正在向磁道序号增加的方向移动。现有一个磁道访问

<!-- image-->

请求序列为 35，45，12，68，110，180，170，195，采用 SCAN 调度（电梯调度）  
算法得到的磁道访问序列是 。A．110，170，180，195，68，45，35，12B．110，68，45，35，12，170，180，195C．110，170，180，195，12，35，45，68D．12，35，45，68，110，170，180，195

5. 系统为某进程分配了 4 个页框，该进程已访问的页号序列为 2,0,2,9,3,4,2,8,2,4,8,4,5。若进程要访问的下一页的页号为 7，依据 LRU 算法，应淘汰页的页号是 。A．2 B．3 C．4 D．8

6. 对记录式文件，操作系统为用户存取文件信息的最小单位是 0A、字符 B、数据项C、记录 D、文件

7. 在一个多进程操作系统中，以下说法正确的是 。A. 如果一个用户进程进入死循环，则其他进程永远不可能获得执行；B. 如果一个用户进程进入死循环，操作系统可以终止该用户进程执行；C. 如果一个用户进程执行“跳转到0地址”的指令后，操作系统内核会立即崩溃；D. 如果一个用户进程执行了“除以0”的指令后，操作系统内核会立即崩溃。

8. 缓冲技术用于 0A、协调主机和设备交换信息的速度差异B、提供主、辅存接口C、减少设备故障D、扩充相对地址空间

9. 实时操作系统追求的目标是 0A.高吞吐率 B.充分利用内存 C. 快速响应 D. 减少系统开销

10. 在操作系统中，用户在使用I/O设备时，通常采用 。A.物理设备名 B.逻辑设备名C.虚拟设备名 D.设备牌号

## 三、 填空题（每个空 1 分，共 10 分）

1. 静态变量通常被装载到 段中，局部变量通常被装载到 _段。

2. 操作系统中虚拟内存机制有效的基础是程序访存的 _原理。

3. 一个进程的页面走向为：5、4、3、2、4、5、4、1、5、2、5、4、5、2、1，系统中共有3个物理内存页，开始时物理页中没有调入任何页面。使用最优页面淘汰算法的缺页次数为_____次，使用FIFO 页面淘汰算法的缺页次数为 _次。

4. 银行家算法是 死锁的方法。

5. 设从磁盘将 1 块数据传送到缓冲区所用时间为 50ms，将缓冲区中数据传送到用户区所用时间为20ms，CPU 处理一个块数据所用时间为60ms。如果有很多块数据需要处理，采用单缓冲区传送磁盘数据，则系统的吞吐能力约为 _块/s。（注：1s=1000ms）。

6. 按数据组织分类，设备分为两类： _和 。

7. 在文件系统中，“.” 通常表示 目录。

## 四、 内存管理（本题共 15 分）

一个 32 位的虚拟存储系统采用两级页表结构，每个页面大小为 4096 字节。该系统逻辑地址中，第22到31位是第一级页表（页目录）的索引，第12位到21位是第二级页表的索引，页内偏移占第0到11位。每个页表（目录）项包含20位物理页框号和12位标志位。

1. 该系统的逻辑地址空间一共有多少字节？（1 分）

2. 该系统第一级页表共有多少页目录项？第二级页表共有多少页表项？（2分）

3. 假设第二级页表的起始逻辑地址为 0x1FC00000，请给出逻辑地址 0x01234567 对应的页目录项的逻辑地址。（3 分）（提示：先根据自映射，找出一级页表的起始逻辑地址）

4. 假设第二级页表的起始逻辑地址为 0x1FC00000，请给一级页表对应的页目录项的逻辑地址。（3分）

5. 假设逻辑地址0x12345678对应的第二级页表的物理地址为0x00007000，请给出该逻辑地址对应的页表项的物理地址、该逻辑地址对应的页目录项中包含的物理页框号。（6分）

## 五、 进程同步与互斥（共 15 分）

一个自动生产线上有 4 个机器人（R1-R4）。R1、R2 分别不断生产 2种不同的零件X、Y。R3 负责不断将 R1、R2 生产的零件X、Y装配成零件Z。R4负责不断将零件Z加工成成品P。有一个共享的零件暂存区，最多可以放10个零件，每次同时仅允许一个机器人访问这个零件暂存区。所有机器人都要通过零件暂存区传递零件。R1、R2 需要等R3 将它们之前生产的零件从暂存区中取走后，才能将新生产的零件放入（也就是说，暂存区中零件 X 和 Y 的数量分别都不会大于 1）。请用 PV 操作给出上述 4 个机器人的同步互斥过程，给出信号量（Semaphore）的定义、初值和必要的注释说明。除了信号量外，不应定义其他变量。

说明：R1 的主要动作包括 produceX()、putX()；R2 的主要动作包括 produceY()、putY()；R3 的主要动作包括 getX()、getY()、produceZ()和 putZ()；R4 的主要动作包括getZ()、produceP()。上述动作应该包含在同步互斥过程中，并在合适的位置添加相应的信号量的PV 操作。上述动作中，只有访问零件暂存区的动作（get或者put 开头的）需要互斥访问暂存区，生产动作（produce开头的）可以并发。

## 六、 进程调度（共 10分）

下表给出的5个进程的到达时间、运行时间、优先级数。

<table><tr><td rowspan=1 colspan=1>进程ID</td><td rowspan=1 colspan=1>到达时间</td><td rowspan=1 colspan=1>运行时间</td><td rowspan=1 colspan=1>优先级数</td></tr><tr><td rowspan=1 colspan=1>A</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>4</td></tr><tr><td rowspan=1 colspan=1>B</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>2</td></tr><tr><td rowspan=1 colspan=1>C</td><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1>5</td></tr><tr><td rowspan=1 colspan=1>D</td><td rowspan=1 colspan=1>6號</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>6號</td></tr><tr><td rowspan=1 colspan=1>E</td><td rowspan=1 colspan=1>8</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>1</td></tr></table>

假设系统中没有其他进程，请填表给出按照先来先服务（FCFS）、最短剩余时间优先（SRTF）、时间片轮转（RR）、静态优先级（Priority）等算法进行调度时，每个时刻在CPU 上运行的进程ID，并求出在各个算法下所有进程的平均等待时间。

注意：

1. 时间片轮转算法（RR）的时间片固定为1。当时间片耗尽后，当前进程会被加入到就绪队列队尾。

2. 优先级数越高，越优先被调度。

3. 不考虑进程上下文切换开销。新进程在到达时刻就处于就绪状态，并可被调度。

4. 进程等待时间指进程到达时刻和进程第一次被调度执行时刻之间等待的时间。

<table><tr><td rowspan=1 colspan=1>时刻</td><td rowspan=1 colspan=1>FCFS</td><td rowspan=1 colspan=1> SRTF</td><td rowspan=1 colspan=1>RR</td><td rowspan=1 colspan=1>Priority</td></tr><tr><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>3</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>4</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>5</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>6個</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>7</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>8</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>9</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>10</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>11</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>12</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr><tr><td rowspan=1 colspan=1>平均等待时间</td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td><td rowspan=1 colspan=1></td></tr></table>

## 七、 死锁（本题共 10 分）

系统中有3个进程（P1，P2，P3），运行这些进程需要4类资源（R1，R2，R3，R4）。在某时刻，各进程已经获得分配的资源、最多还需要的资源以及当前可用资源情况如图所示。

<table><tr><td rowspan=1 colspan=9>已分配资源                 最多还需要的资源</td></tr><tr><td rowspan=1 colspan=1>进程</td><td rowspan=1 colspan=1>R1</td><td rowspan=1 colspan=1>R2</td><td rowspan=1 colspan=1>R3</td><td rowspan=1 colspan=1>R4</td><td rowspan=1 colspan=1>R1</td><td rowspan=1 colspan=1>R2</td><td rowspan=1 colspan=1>R3</td><td rowspan=1 colspan=1>R4</td></tr><tr><td rowspan=1 colspan=1>P1</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>1</td></tr><tr><td rowspan=1 colspan=1>P2</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>0</td></tr><tr><td rowspan=1 colspan=1>P3</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>0</td></tr></table>

<table><tr><td rowspan=1 colspan=4>当前可用资源</td></tr><tr><td rowspan=1 colspan=1>R1</td><td rowspan=1 colspan=1>R2</td><td rowspan=1 colspan=1>R3</td><td rowspan=1 colspan=1>R4</td></tr><tr><td rowspan=1 colspan=1>2</td><td rowspan=1 colspan=1>1</td><td rowspan=1 colspan=1>0</td><td rowspan=1 colspan=1>0</td></tr></table>

（1） 如果3个进程同时发出最大资源请求，请画出资源分配图，并用资源分配图化简的方法检测是否存在死锁。（本小题5分）

（2） 如果此时进程P2 请求1个R1 资源，为了避免产生死锁，请根据银行家算法判断是否可以满足P2 的请求。（本小题5分）

## 八、 文件系统（本题共 10 分）

很多类Unix文件系统都基于索引方式对文件进行组织管理。一般采用i节点（inode）存储文件或者目录的属性信息和数据所在的物理块信息。

（1）如果某采用索引的文件系统采用 512 字节大小的数据块和 4 字节的数据块地址。每个i 节点包括10个直接索引，1个一级间接索引和1个二级间接索引和1个三级间接索引。该文件系统中文件最大为多少 KB？（本小题 5 分）

（2）若要读取文件“/tmp/foo”,请给出从根目录开始进行文件查找和读取数据的主要处理步骤。提示：为了简化，假定根目录内容可直接从内存读取，且不考虑使用间接索引情况。（本小题 5 分）