---
updated: 2026-10-22 00:25
created: 2026-10-21 01:02
tags:
---
# 介绍
**Dart**的**泛型**允许在定义类、函数和集合时使用**类型参数**，使代码能够处理不同的数据类型，提高代码的**复用性**和**类型安全性**。
# 使用方式
使用`<T>`定义**类型参数**，在定义类时使用**类型参数**，使类能够处理不同的数据类型。
```dart
class Box<T> {
	T value;
	Box(this.value);

	T getValue() { return value; }
}

// 尽量不要用 Box box = Box("Tom") 的方式，会被推导成动态类型
Box<String> box = Box("Tom");
```

在定义**函数**时使用**类型参数**，使函数能够处理不同的数据类型。
```dart
T getValue<T>(T value) {
	return value;
}

String name = getValue<String>("Tom");
// 可以让 Dart 自动推导类型
String name = getValue("Tom");
```

在**集合**中使用泛型，可以通过指定**类型参数**限制集合中元素的类型。
```dart
List<String> names = ["Tom", "Jerry"];
List<int> numbers = [1, 2, 3];
```
# 相关