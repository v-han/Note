---
updated: 2026-10-20 21:54
created: 2026-10-19 22:00
tags:
---
# 介绍
**Dart**中**类**的**构造函数**，主要分为**普通构造函数**(Generative)、**命名构造函数**(Named)，**常量构造函数**(Constant)和**工厂构造函数**(Factory)。
# 使用方式
**普通构造函数**使用类同名方法作为**构造函数**，用于创建类的实例，并初始化对象的属性。**普通构造函数**不允许重载。
```dart
class Person {
	// 属性省略
	Person(String name, int age) {
	    this.name = name;
	    this.age = age;
	}
	// 可以使用 初始化列表 的方式，和上面等价，后面还能接正常的函数
	// Person(String name, int age)
	//	: this.name = name, this.age = age;
	
	// 可以使用 初始化形式参数 语法糖方式方式简化，和上面等价
	// Person(this.name, this.age);
}

Person person = Person("Tom", 18);
```

**默认构造函数**是**普通构造函数**的特殊情况，在类没有**构造函数**的情况下自动生成一个**无参构造函数**。

**命名构造函数**使用`类名.名称`定义构造函数，允许定义不同的**构造函数**。
```dart
class Person {
	// 属性省略，这里使用初始化列表来初始化对象
	Person.tom(): this.name = "Tom", age = 18;

	// 也可以和正常函数一样
	// Person.tom(): name = "Tom", age = 18 { // 语句 };
}

Person person2 = Person.tom();
```
# 相关
构造函数也是函数，也可以使用[[Dart函数参数|函数参数]]。