---
updated: 2026-10-24 01:13
created: 2026-10-23 23:16
tags:
---
# 介绍
**StatelessWidget**是无状态的**Widget子类**，自身不保存可变状态，界面由传入的配置决定。
# 使用方式
定义一个类继承**StatelessWidget**类，并重写`build`方法，返回需要展示的**Widget**。`build`方法接收一个**BuildContext**参数，用于表示当前**Widge**t在**Widget树**中的位置。
```dart
class MyWidget extends StatelessWidget {
	@override
	Widget build(BuildContext context) {
	    return Text("Hello Flutter");
	}
}
```

> [!NOTE]
> `build`方法由**Flutter**框架自动调用，用于构建用户界面，通常不需要手动调用。当**Widget**需要**构建**或**更新**界面时，**Flutter**会执行对应的`build`方法。
# 相关