---
created: 2026-10-19 21:36
updated: 2026-10-21 00:51
tags:
---
# 介绍
**Dart**的[[OOP|面向对象]]操作。
# 使用方式
使用`class`定义一个**类**，可以为其添加**属性**与**方法**。
```dart
class Person {
	// 属性
	String name = "Tom";
	int age = 18;

	// 方法
	void sayHello() {
		// 可以用 this 指定自己的属性
	    print("Hello, I'm ${this.name}");
  }
}
```

使用[[Dart构造函数|构造函数]]实例化对象。
```dart
Person person = Person();
```

使用`.`访问对象的**属性**与**方法**。
```dart
String name = person.name;
person.sayHello();
```

**Dart**使用`_`区分**公有**与**私有**成员，**私有成员**只能在所属的[[Dart库|库]]使用。
```dart
// 私有属性
String _name = "";
// 私有方法
int _agePlus() { this.age += 1; }
```
# 相关
[[Dart继承]]
[[Dart混入]]