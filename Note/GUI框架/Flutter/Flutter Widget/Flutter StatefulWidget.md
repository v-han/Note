---
updated: 2026-10-26 14:21
created: 2026-10-23 23:18
tags:
---
# 介绍
**StatefulWidget**是有状态的**Widget子类**，可以通过关联的`State`对象保存可变状态，并根据状态变化更新界面。
# 使用方式
定义一个类继承**StatefulWidget**，并重写`createState`方法，创建对应的**State**对象。
```dart
class MyWidget extends StatefulWidget {
	// <MyWidget> 这里填当前 Widget
	@override
	State<MyWidget> createState() => _MyWidgetState();
}
```

再定义一个类继承**State**，并重写`build`方法构建用户界面。
```dart
class _MyWidgetState extends State<MyWidget> {
	// 可定义 State 的状态
	int count = 0;
	
	@override
	Widget build(BuildContext context) {
		return Text("Hello Flutter");
	}
}
```

使用`setState`方法修改状态并通知**Flutter**重新构建界面。
```dart
setState(() {
    count++;
});
```
# 相关
[[Flutter StatefulWidget生命周期|有状态组件生命周期]]