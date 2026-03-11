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
## linux命令
+ 运行指令：`.\XXX` 必须要有目录，不能为空，否则只会在PATH中寻找
+ 增加运行权限（如.sh）：`chmod +x <文件名>`，`chmod +x *.sh`使用通配符

## Ctags
+ 快速跳转到函数/类/结构体定义处。
+ 在目录下运行`ctags -R *`
+ 跳转`Ctrl + ]` 返回`Ctrl + O`

## Tmux
终端窗口和进程分离，允许显示多个进程运行
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