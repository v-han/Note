---
created: 2026-10-22 13:36
updated: 2026-10-22 21:35
tags:
---
# 介绍
**Dart**的**Future**表示一个**异步操作**的结果，该操作会在未来某个时刻完成，并返回一个结果或异常。
**Future**有三种状态：**尚未完成**，**成功完成**，**执行失败**。
# 使用方式
使用`Future`构造函数创建一个**Future**对象，传入一个**匿名函数**作为回调函数，将回调函数安排到[[Dart事件循环|事件队列]]中执行。
```dart
Future<String> future = Future(() {
	return "Hello";
});
```

或在函数声明后添加`async`关键字，将其声明为**异步函数**，使其返回一个**Future**对象。
```dart
Future<String> getData() async {
	return "Hello";
}
// 调用异步函数获得 Future 对象
var future = getData();
```

使用**Future**方法为异步操作注册**回调函数**，在**Future**完成或发生异常时执行对应的操作，这些方法可以链式调用。
```dart
Future(() {
	return "Hello";
}).then((value) {      // 正常完成时的回调函数
	print(value);
}).catchError((error) { // 错误处理回调函数
	print(error);
}).whenComplete(() {   // 完成后(包含错误)的回调函数
	print("执行结束");
});
// 还可以使用 timeout() 来设置等待时间，超时返回超时异常
```

使用`await`关键字暂停当前**异步函数**，等待对应的**Future**完成。等待期间，**事件循环**可以继续调度其他任务。
```dart
Future<String> getData() async {
	// 运行到此处会暂停当前函数，执行外部同步代码
	await Future.delayed(Duration(seconds: 2));
	// 等待 Future 完成后继续执行当前函数后续代码
	return "Hello Dart";
}
```

> [!NOTE]
> `await`通常只能在使用`async`声明的函数中使用。
> 
> 不使用`await`时会继续执行当前函数的**同步代码**。
# 相关