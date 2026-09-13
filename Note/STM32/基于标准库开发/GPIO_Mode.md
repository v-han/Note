---
updated: 2026-09-10 23:56
created: 2026-07-26 14:56
tags:
---
# 介绍
**基于标准库开发**的[[GPIO 标准库配置|GPIO]]的**工作模式**配置。
# 使用方式
在**GPIO**初始化结构体中为`GPIO_Mode`赋值。
```C
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP
```

**GPIO**的**工作模式**取以下枚举类的值。
```c
typedef enum { 
	GPIO_Mode_AIN = 0x0,          // 模拟输入
	GPIO_Mode_IN_FLOATING = 0x04, // 浮空输入
	GPIO_Mode_IPD = 0x28,         // 下拉输入
	GPIO_Mode_IPU = 0x48,         // 上拉输入
	GPIO_Mode_Out_OD = 0x14,      // 开漏输出
	GPIO_Mode_Out_PP = 0x10,      // 推挽输出
	GPIO_Mode_AF_OD = 0x1C,       // 复用开漏输出
	GPIO_Mode_AF_PP = 0x18        // 复用推挽输出
} GPIOMode_TypeDef;
```
# 相关
[[GPIO工作模式]]