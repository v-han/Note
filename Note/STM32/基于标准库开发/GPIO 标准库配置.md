---
updated: 2026-09-13 00:25
created: 2026-09-10 14:59
tags:
---
# 介绍
[[GPIO]]的**标准库**的配置方式。
# 使用方式
按以下的**GPIO**初始化结构体配置**GPIO**。
```C
typedef struct {
	// GPIO 引脚
	uint16_t GPIO_Pin;
	// GPIO 速率
	GPIOSpeed_TypeDef GPIO_Speed;
	// GPIO 模式
	GPIOMode_TypeDef GPIO_Mode;
} GPIO_InitTypeDef;
```

配置使用的[[GPIO_Mode|GPIO模式]]、[[GPIO_Pin|引脚]]和**速率**，并初始化GPIO。
```C
GPIO_InitTypeDef GPIO_InitStructure;
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_13;
GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
	
// 使用定义的端口结构体初始化 GPIO
GPIO_Init(GPIOC, &GPIO_InitStructure);
```
# 相关