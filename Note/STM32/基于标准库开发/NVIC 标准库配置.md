---
updated: 2026-09-13 16:13
created: 2026-09-13 00:33
tags:
---
# 介绍
[[NVIC]]的**标准库**的配置方式。
# 使用方式
使用前需要设定[[NVIC分组]]，其对应的取值与[[NVIC分组]]中的分组方式一致(分组0 -> `NVIC_PriorityGroup_0`)。
```c
NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
```

按以下的**NVIC**初始化结构体配置**NVIC**。
```c
typedef struct {
	// NVIC 中断通道
	uint8_t NVIC_IRQChannel;
	// NVIC 抢占优先级
	uint8_t NVIC_IRQChannelPreemptionPriority;
	// NVIC 响应优先级
	uint8_t NVIC_IRQChannelSubPriority;
	// NVIC 状态
	FunctionalState NVIC_IRQChannelCmd;
} NVIC_InitTypeDef;
```

配置使用的**NVIC中断通道**、**抢占优先级**、**响应优先级**(具体取值看上面的分组)和**状态**，并初始化**NVIC**。
```c
NVIC_InitTypeDef NVIC_InitStructure;
NVIV_InitStructure.NVIC_IRQChannel = EXTI15_10_IRQn;
NVIV_InitStructure.NVIC_IRQChannelCmd = ENABLE;
NVIV_InitStructure.NVIC_IRQChannelPreemptionPriority = 1;
NVIV_InitStructure.NVIC_IRQChannelSubPriority = 1;
NVIC_Init(&NVIC_InitStructure);
```
# 相关