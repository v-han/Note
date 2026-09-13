---
updated: 2026-09-10 23:51
created: 2026-07-26 21:47
tags:
---
# 介绍
**基于标准库开发**的[[GPIO 标准库配置|GPIO]]的**引脚**配置。
# 使用方式
在**GPIO**初始化结构体中为`GPIO_Pin`赋值。
```c
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_0;
// 使用 | 来选中多个引脚
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_0 | GPIO_Pin_1;
```

**GPIO**的**引脚**配置本质是16位的无符号数。
```c
#define GPIO_Pin_0  ((uint16_t)0x0001)
#define GPIO_Pin_1  ((uint16_t)0x0002)
#define GPIO_Pin_2  ((uint16_t)0x0004)
#define GPIO_Pin_3  ((uint16_t)0x0008)
// 省略中间的
#define GPIO_Pin_15  ((uint16_t)0x8000)
#define GPIO_Pin_All ((uint16_t)0xFFFF)
```

> [!WARNING]
> 使用时注意查看手册，有的端口有别的功能，例如调试等。这些端口最好不要占用。
# 相关