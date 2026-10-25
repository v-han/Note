---
updated: 2026-10-23 00:10
created: 2026-10-22 00:29
tags:
---
# 介绍
**Dart**默认在单个**隔离单元**(Isolate)中以**单线程**方式执行代码，需要通过**异步操作**避免等待耗时操作时**阻塞**后续代码的执行。
**Dart**主要通过[[Dart事件循环|事件循环]]来调度和管理异步任务。
# 使用方式
使用[[Dart Future|Future]]创建**异步事件**或**微任务**。
```dart
// 创建异步任务，将回到函数放到事件队列
Future(() {
  print("Event");
});

// 创建微任务，将回调函数放到微任务队列
Future.microtask(() {
  print("Microtask");
});
```

> [!NOTE]
> 也可以使用`scheduleMicrotask`创建**微任务**，但该函数返回`void`，无法直接链式调用**Future**的方法。
> ```dart
> scheduleMicrotask(() {
> 	print("Hello");
> });
> ```
# 相关