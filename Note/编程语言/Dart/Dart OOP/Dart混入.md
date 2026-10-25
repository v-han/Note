---
updated: 2026-10-21 01:00
created: 2026-10-21 00:51
tags:
---
# 介绍
**Dart**的**混入**(Mixin)可以将一个**类**中的**属性**和**方法**复用到其他类中。
# 使用方式
使用`mixin`关键字定义**混入**。
```dart
mixin Swim {
	void swim() {
		print("Swimming");
	}
}
```

使用`with`关键词**混入**当前类中，一个**类**可以进行多个**混入**。
```dart
class Student extends Person with Swim {
	Student(String name) : super(name);
}

void main() {
	Student student = Student("Tom");
	student.swim();
}
```

> [!NOTE]
> 若多个**混入**有相同的**属性**或**方法**，**后混入**的会覆盖**先混入**的。

使用`on`关键字可以限制使用它的**类**。
```dart
// 只有 Person 及其子类可以使用该混入
mixin Fly on Person {
	void fly() {
	    print("$name is flying");
	}
}

```
# 相关