---
updated: 2026-10-20 22:43
created: 2026-10-19 22:55
tags:
---
# 介绍
**Dart**中**类**的**继承**。**Dart**属于**单继承**，一个**类**只能有一个直接**父类**。
# 使用方式
使用`extends`实现**继承**，**子类**拥有**父类**所有的**属性**与**方法**。
```dart
class Student extends Person {
	String school = "XXSchool";

	void study() {
	    print("I'm studying at $school");
	}
}
```

**子类**不继承**父类**的[[Dart构造函数|构造函数]]，需使用`super`关键字调用**父类**的**构造函数**。
```dart
class Student extends Person {
	// 其他省略
	// super 需要放在普通属性初始化之前，且父类要有对应的构造函数
	Student(String name, int age, String school): 
		super(name, age), this.school = school;
		
	//也支持 初始化形式参数 的方式，父类要有对应的构造函数
	Student(super.name, super.age, this.school);
}
```

使用`super`访问**父类**的**属性**与**方法**。
```dart
// 访问父类属性
super.name;
// 访问父类方法
super.sayHello();
```

使用`@override`注解重写父类方法。
```dart
class Student extends Person {
	// 其他省略
	@override
	void sayHello() {
	    print("Hello, I'm ${super.name} from ${this.school}");
	}
}
```
# 相关
[[Dart多态]]
[[Dart抽象类]]
[[Dart接口]]