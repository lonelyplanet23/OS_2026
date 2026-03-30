## 程序不等于进程
简化理解：A process is a program in excucation

例如**同时运行的两个word文件**是**两个不同的进程** 进程≠程序

**进程地址空间**
+ 进程加载到内存中的地址范围

一个进程往往包含: Text(指令) Data(常量或者全局变量) Stack Heap（临时变量）

附: C/ Rust 编译型语言 Js Python 解释型语言，解释型语言运行的是解释器，其代码文件往往载入到Heap中作为数据；而编译型语言则是编译成机器码后载入到Text中。