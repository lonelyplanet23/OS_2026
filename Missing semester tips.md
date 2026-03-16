## Make 与 MakeFILE

+ make的核心功能：**根据时间戳自动判断哪些部分需要重新编译，每次只重新编译必要部分**
+ MakeFile:人工指导文件编译链接成可执行文件
```MakeFile
target: dependencies
    command 1
    command 2
    ...
    command n
```
+ $@ 代表当前目标文件名（如 out、case_add），是 Makefile 最常用的自动变量；
+ $^ 代表所有依赖文件（如 case_all 的依赖是 4 个样例文件）；

## linux命令
+ 运行指令：`.\XXX` 必须要有目录，不能为空，否则只会在PATH中寻找
+ 增加运行权限（如.sh）：`chmod +x <文件名>`，`chmod +x *.sh`使用通配符
+ < 是输入重定向、> 是输出重定向
+ cat 命令用于拼接文件内容，是合并多个文件的基础操作。
### sed 指令
+ 多行输出连续行数 `sed -n '<起始行>,<终止行>p' <文件名>`
+ 多行输出非连续 `sed -n '<行1>p; <行2>p....' <文件名>`

## Ctags
+ 快速跳转到函数/类/结构体定义处。
+ 在目录下运行`ctags -R *`
+ 跳转`Ctrl + ]` 返回`Ctrl + O`

## Tmux
终端窗口和进程分离，允许显示多个进程运行
`Ctrl+B 松开后迅速 SHIFT+5` 左右切屏
`tmux ls`查看会话名
`tmux a -t 会话名` 恢复到原来的会话


## git
+ `git restore`
    + `git restore <filename>` 未暂存时，回到上一次commit的状态
    + `git restore --staged <filename>` 暂存后，取消暂存

+ `git checkout`
  + `git checkout lab<x>` 切换分支
## Bash shell
+ 命令行环境与解释器，类似于win中的批处理文件.bat
`#!/bin/bash`选择bash解释器
+ 输出： `echo`
+ 变量：`a=1` 不允许有空格
  + 整数计算比较都需要`(())`
+ 函数返回 ` return $(($1 + $2))`注意外面也需要`$`

## GCC 编译器
`gcc <文件名> -o <可执行程序名>` 生成可执行文件
`gcc -g <文件名> -o <可执行程序名>` 生成目标程序的 Debug 版本
`gcc <文件名>`默认生成一个out文件

## 在 Vim 内部重编
在 Vim 的末行模式（按下 :）输入：

+ %: 代表当前文件名（如 hello.c）。

+ %<: 代表去掉后缀的文件名（如 hello）。

+ !: 告诉 Vim 这是一条外部 Shell 命令。

## GDB 调试器
> allows you to see what is going on `inside' another program **while it executes**-- or what another program was doing at the moment it crashed.
### 第一步
+ `gcc -g <file_name> -o <exe_name>` 生成debug版本的执行文件（否则的话是release版本）
`gdb -tui <exc_file>` 启动TUI界面

![4](assets/image-4.png)
### 基础调试
+ 继续：对应 GDB 中的 continue 指令，一直执行到断点或者结束或者输入
+ 步过：对应 GDB 中的 next 指令，执行当前所在的行，而**跳过当前行中的任何函数调用**
+ 步入：对应 GDB 中的 step 指令
+ 步出：对应 GDB 中的 finish 指令，从函数内部的执行跳出直接给出返回值。
+ 重启：对应 GDB 中的 start 指令（在程序运行中使用）：跳转
+ 停止：对应 GDB 中的 kill 指令

### 断点与参数
+ 查看行号内容：`list [position]`：`list <line nunmber>`、`list <file>:<line number>`、`list <function name>` 和 `list <file>:<function name>`
+ 设置断点`break [position]`
+ 设置临时断点` tbreak` 暂停一次自动删除，`start`本质就是在main函数设置一个临时断点。
+ 避免重复在这一断点处暂停：`disable breakpoints [num]...` num 需要查看断点编号`info breakpoints`
+ 删除断点`delete breakpoints [num]...`
+ 运行时加参数`start [arg]...` `run [arg]...`

### 条件调试
+ 条件断点：`break/tbreak <position> if <condition>`
+ 没有显式计数的条件断点：`tbreak <position>`   `ignore <num> <times>` 忽略前K-1次的断点。

### 观察点-断点特殊类型
**方便找到异常值产生位置！**
+ `watch <expression>` 设置观察点：当表达式取值发生变化，就会停下中断
+ `awatch arr[n]` 设置访问观察点：对于一个N长度的数组，这可以观察是否发生数组越界的情况。
+ `rwatch <expression>`	设置读观察点:

### 查看运行时数据
+ `arr[<index>]@<len>` 表示显示数组中从`<index>` 处开始长度为` <len> `的范围内各元素的值。
+ `disassemble -m <addr> 或<函数名>` 显示对应代码的汇编。
+ `backtrace` `backtrace -n` 追溯显示栈帧，注意是负数！
+ `frame <num>`查看第几个栈帧，追溯一些变量
+ `print <expr>` `p <expr>`

### 修改运行程序
+ `set <var> = <expr>`
+ `return [expr]` 立即以指定的返回值返回
+ `jump [pos]` 立即跳到（行或者函数）