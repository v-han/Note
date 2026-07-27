---
updated: 2026-07-24 20:15
created: 2026-07-24 20:13
tags:
---
# 介绍
[[基于寄存器开发]]的点灯项目。
# 开发步骤
在`main.c`文件中编写以下代码。
```C
#include "stm32f10x.h"

int main(void) {
	// 配置时钟
	RCC->APB2ENR = 0x00000010;
	
	GPIOC->CRH = 0x00300000;
	GPIOC->ODR = 0x00000000;
	
	// 用死循环保持状态
	while(1) {}
}

```

编译并下载到STM32开发板上。
# 相关