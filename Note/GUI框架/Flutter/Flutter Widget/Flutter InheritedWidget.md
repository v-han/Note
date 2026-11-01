---
updated: 2026-10-26 16:23
created: 2026-10-26 15:01
tags:
---
# 介绍
**继承式组件**(InheritedWidget)是**Flutter**中用于在**Widget树**中向下共享数据的**Widget**基类
# 使用方式
定义一个类继承**InheritedWidget**类，通过属性保存需要共享的数据。并重写`updateShouldNotify`方法，判断新旧**Widget**的共享数据是否发生变化，以决定是否通知依赖该**Widget**的子孙组件更新。
```dart
class MyData extends InheritedWidget {
	final int count;

	const MyData({
	    super.key,
	    required this.count,
	    required super.child,
	});

	// 当上层组件重新构建并更新当前 InheritedWidget 时
	// 会用该方法来判断是否通知子组件更新
	@override
	bool updateShouldNotify(MyData oldWidget) {
	    return count != oldWidget.count;
	}
}
```

其子孙组件可通过**Widget树**获取祖先组件**共享的数据**并**建立依赖关系**。
```dart
class MyWidget extends StatelessWidget {
	@override
	Widget build(BuildContext context) {
		// 查找最近 MyData 祖先组件，并共享数据和建立依赖
		// 因此该组件需要是 MyData 的子孙组件
	    final data =
		    context.
		    dependOnInheritedWidgetOfExactType<MyData>();

	    return Text("${data?.count}");
	}
}
```
# 相关