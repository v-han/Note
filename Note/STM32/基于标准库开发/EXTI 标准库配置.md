---
updated: 2026-09-13 16:09
created: 2026-09-10 15:42
tags:
---
# 介绍
[[EXTI]]的**标准库**配置方式。
# 使用方式
按一下的**EXTI**初始化结构体配置**EXTI**。
```c
typedef struct {
	// EXTI 输入引脚
	uint32_t EXTI_Line;
	// EXTI 工作模式
	EXTIMode_TypeDef EXTI_Mode;
	// EXTI 触发方式
	EXTITrigger_TypeDef EXTI_Trigger;
	// EXTI 状态
	FunctionalState EXTI_LineCmd;
} EXTI_InitTypeDef;
```

**EXTI**的引脚为从[[AFIO]]接入的引脚。

**EXTI**的**工作模式**如下。
```c
typedef enum {
	// 中断触发
	EXTI_Mode_Interrupt = 0x00,
	// 事件触发
	EXTI_Mode_Event = 0x04
} EXTIMode_TypeDef;
```

**EXTI**的**触发方式**如下。
```c
typedef enum {
	// 上升沿触发
	EXTI_Trigger_Rising = 0x08,
	// 下降沿触发
	EXTI_Trigger_Falling = 0x0C,
	// 上升沿和下降沿都触发
	EXTI_Trigger_Rising_Falling = 0x10
} EXTITrigger_TypeDef;
```

**EXTI**的状态如下。
```c
typedef enum {
	DISABLE = 0,
	ENABLE = !DISABLE
} FunctionalState;
```

配置使用的**EXTI引脚**、**工作模式**、**触发方式**和**状态**，并初始化**EXTI**。
```c
EXTI_InitTypeDef EXTI_InitStructure;
EXTI_InitStructure.EXTI_Line = EXTI_Line14;
EXTI_InitStructure.EXTI_LineCmd = ENABLE;
EXTI_InitStructure.EXTI_Mode = EXTI_Mode_Interrupt;
EXTI_InitStructure.EXTI_Trigger = ;
EXTI_Init(&EXTI_InitStructure);
```
# 相关