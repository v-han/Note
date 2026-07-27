---
updated: 2026-07-26 22:12
created: 2026-07-26 21:47
tags:
---
# 介绍
# 使用方式
在定义的**GPIO**配置结构体中配置**GPIO_Pin**的值。
```C
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_0;
```

在使用多个引脚的使用可以使用`|`符号连接。
```C
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_0 | GPIO_Pin_1;
```

> [!NOTE]
> 这是按位与操作，将对应位的值变为1表示使用该端口。

若需要使用全部端口可以使用`GPIO_Pin_ALL`。
```C
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_ALL;
```

> [!WARNING]
> 使用时注意查看手册，有的端口有别的功能，例如调试等。这些端口最好不要占用。
# 相关