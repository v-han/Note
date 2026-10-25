---
updated: 2026-10-21 00:54
created: 2026-10-20 22:43
tags:
---
# 介绍
**Dart**没有专门的**接口**，但每个类都隐式定义了一个**接口**。
# 使用方式
每个类都隐式定义了**接口**，使用`implements`关键字实现**接口**。实现**接口**需要重新实现**接口**的**所有成员**(包括**属性**)。
```dart
class Person {
	String name = "Tom";

	void sayHello() {
	    print("Hello, I'm ${this.name}");
  }
}

// 使用 implements 实现接口
class Student implements Person {
	@override
	String name = "Jerry";

	@override
	void sayHello() {
		print("Hello, I'm ${this.name}, a student");
	}
}
```
# 相关