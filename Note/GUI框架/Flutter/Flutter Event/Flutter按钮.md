---
updated: 2026-10-26 18:57
created: 2026-10-26 17:51
tags:
---
# 介绍
**Flutter**提供了多种内置的按钮组件，用于响应用户的点击操作。
# 使用方式
**Flutter**有以下常见的按钮组件：**TextButton**、**ElevatedButton**、**OutlinedButton**、**FilledButton**、**IconButton**、**FloatingActionButton**。

通过为**按钮组件**的事件属性设置**匿名函数**，注册对应事件的**回调函数**。
```dart
TextButton(
	onPressed: () {
	    print("按钮被点击");
	},
	child: Text("点击按钮"),
)
```

> [!NOTE]
> 除此之外还能通过设置属性的方式配置**其他事件**和**样式**(style)等设置。

对于常见的**Material**按钮，当`onPressed`和其他可启用按钮的交互回调均为`null`时，按钮会进入禁用状态。
# 相关