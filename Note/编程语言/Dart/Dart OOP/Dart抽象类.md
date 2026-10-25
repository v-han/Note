---
created: 2026-10-20 22:34
updated: 2026-10-21 00:49
tags:
---
# 介绍
**Dart**中的**抽象类**不能直接实例化。通常作为**父类**，让**子类**继承并实现其中的**抽象方法**。
# 使用方式
使用`abstract`关键字定义**抽象类**。
```dart
abstract class Person {
	// 其他省略
	// 抽象类可以有构造方法，但不能实例化
	Person(this.name);
	// 抽象方法，可以没有实现
	void sayHello();
}
```

使用`extends`继承**抽象类**，并实现**抽象方法**。
```dart
class Student extends Person {
	// 其他省略
	// 实现抽象方法
	@override
	void sayHello() {
		print("Hello, I'm $name");
	}
}
```
# 相关