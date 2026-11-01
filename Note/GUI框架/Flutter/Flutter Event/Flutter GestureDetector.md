---
updated: 2026-10-26 17:43
created: 2026-10-26 16:49
tags:
---
# 介绍
**GestureDetector**是**Flutter**中专门用于检测手势的组件，可以为普通组件添加点击、双击、长按、拖动等事件。
# 使用方式
用**GestureDetector**组件包裹需要监听手势的组件，并通过对应的事件属性注册**回调函数**。
```dart
GestureDetector(
	onTap: () {
	    print("单击");
	},
	onDoubleTap: () {
		print("双击");
	},
	onLongPress: () {
	    print("长按");
	},
	child: Text("点击区域"),
)
```
# 相关