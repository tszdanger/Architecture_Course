# 演示实验介绍

本目录为符号解析练习的验证演示（对应PPT 20页)，请大家首先完成PPT上的练习（完成该表格）。然后可以将swap.c和m.c编译之后，反汇编查看它的符号表验证你的想法是否正确。

具体步骤：

```shell
linux > gcc -Wall -Og -c swap.c
linux > gcc -Wall -Og -c m.c
linux > objdump -t swap.o		> swapsym.d
linux > objdump -t m.o 		    > msym.d
```

### shell instruction 
objdump 
查看符号表： objdump -t xxx.so 。-T 和 -t 选项在于 -T 只能查看动态符号，如库导出的函数和引用其他库的函数，而 -t 可以查看所有的符号，包括数据段的符号
objdump -t obj 输出目标文件的符号表()
objdump -h obj 输出目标文件的所有段概括()
objdump -j .text/.data -S obj 输出指定段的信息，大概就是反汇编源代码把
objdump -S obj C语言与汇编语言同时显示

### File

swap.c 
m.c PPT上作为练习的示例程序
Makefile 
以下两个.d文件为包含符号表信息的swap.o及m.o反汇编文件：
swap-symtab.d
m-symtab.d

### Command
本目录下的命令使用Makefile管理
如需生成所有的文件，直接执行`linux > make swap`
清理所有中间文件，执行`linux > make clean`
GCC命令其他可参考Makefile
