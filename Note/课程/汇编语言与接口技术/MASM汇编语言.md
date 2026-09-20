---
updated: 2026-04-29 23:28
created: 2026-04-22 15:06
tags:
---
# 介绍
# 格式
MASM汇编代码格式：
```asm
DATAS SEGMENT
    ;此处输入数据段代码  
DATAS ENDS

STACKS SEGMENT
    ;此处输入堆栈段代码
STACKS ENDS

CODES SEGMENT
    ASSUME CS:CODES,DS:DATAS,SS:STACKS
START:
    MOV AX,DATAS
    MOV DS,AX
    ;此处输入代码段代码
    MOV AH,4CH
    INT 21H
CODES ENDS
    END START
```

`STACK`：堆栈段。
`DATA`：数据段。
`CODE`：代码段。

[[MASM常量，运算符和表达式]]
[[MASM变量及其属性]]
[[MASM调试]]

> [!NOTE]
> `MOV AX, [0]` 会被编译器认为是 `MOV AX，0`。
> 汇编和debug的处理结果不同。
> 正确的写法为：`MOV AX, DS:[0]`
> 



| 目的         | 相关指令                     | 指令性质 | 指令执行者 |
| ---------- | ------------------------ | ---- | ----- |
| 通知编译器一个段结束 | 段名 ENDS                  | 伪指令  | 编译器   |
| 通知编译器程序结束  | END                      | 伪指令  | 编译器   |
| 程序放回       | MOV AX， 4C00H<br>INT 21H | 汇编指令 | CPU   |

语句类型：
1. 硬指令语句：能够产生目标代码，CPU可以执行。
2. 伪指令语句：不产生目标代码，只告诉编译器如何编译代码。
3. 宏指令语句：一个指令序列，出现宏指令的时候用对应的指令序列的目标代码替代。

[[LOOP指令]]

程序返回：
 ```asm
 MOV AX, 4C00H
 INT 21H
 ```

要在代码段之后添加这段代码，表示程序退出。

[[内中断]]
# 相关