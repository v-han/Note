---
updated: 2026-07-26 15:15
created: 2026-07-26 14:56
tags:
---
# 介绍
[[基于标准库开发]]的[[GPIO工作模式]]配置。
# 使用方式
在定义的**GPIO**配置结构体中配置**GPIO_Mode**的值。
```C
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP
```

这样就将GPIO的引脚配置为推挽输出模式。
# 工作模式

| 枚举类                       | [[GPIO工作模式\|对应模式]] |
| ------------------------- | ------------------ |
| **GPIO_Mode_AIN**         | 模拟输入               |
| **GPIO_Mode_IN_FLOATING** | 浮空输入               |
| **GPIO_Mode_IPD**         | 下拉输入               |
| **GPIO_Mode_IPU**         | 上拉输入               |
| **GPIO_Mode_OUT_OD**      | 开漏输出               |
| **GPIO_Mode_OUT_PP**      | 推挽输出               |
| **GPIO_Mode_AF_OD**       | 复用开漏输出             |
| **GPIO_Mode_AF_PP**       | 复用推挽输出             |

# 相关