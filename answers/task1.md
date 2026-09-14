# Task 1：从 C 源码到可执行文件

请用自己的语言简要说明下面几个阶段分别做了什么：

1. 预处理  
在我看来，预处理阶段就是为编译做好准备工作，使得编译能更方便的进行。它将.c/.cpp文件翻译为.i/.ii文件。包括展开头文件，替换宏定义，方便编译时直接调用。因此文件的大小会暴增，根目录下的test.i由14行变为接近900行。
2. 编译  
编译分为前后端，前端是词法、语法、语义分析，中间代码生成，后端是中间代码优化，目标代码生成和优化。编译过程会把源代码的高级语言翻译为汇编语言，如果代码存在特定错误会在这个阶段报错。
```bash
❯ cat test.s
        .file   "test.c"
        .text
        .section        .rodata
.LC0:
        .string "nihao"
        .text
        .globl  main
        .type   main, @function
main:
.LFB0:
        .cfi_startproc
        pushq   %rbp
        .cfi_def_cfa_offset 16
        .cfi_offset 6, -16
        ............
```
3. 汇编  
将汇编语言翻译为cpu能读懂的机器码。生成的文件是二进制文件，因此打开会是一堆乱码。
```bash
❯ cat test.o
UH��H��H�H�Ǹ��E��E����nihaoGCC: (GNU) 16.2.1 20260810 GNU��zRx
l                                                            A�C
test.cmainprintf
                ��������▒�������� .symtab.strtab.shstrtab.rela.text.data.bss.rodata.comment.note.GNU-stack.note.gnu.property.rela.eh_frame @1�0
         ▒&qq1q90wB�R�j�e@�▒
                               ▒�
                                ▒       ��t⏎  
```                                
4. 链接
顾名思义，这个阶段把先前得到的.o文件和库文件链接起来，合并成最后的可执行文件。

建议控制在 300～500 字，不需要展开复杂细节。
