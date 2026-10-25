---
created: 2026-10-20 22:18
updated: 2026-10-20 22:31
tags:
---
# 介绍
**Dart**中的**多态**(Polymorphism)是**父类**类型的变量可以引用不同**子类**的对象，根据对象的实际类型执行对应调用被重写的方法。
# 使用方式
使用**父类**变量引用**子类对象**，并使用**子类**的方法。
```dart
Person person = Student("Tom", 20, "xxSchool");
// 调用的是子类重写的 sayHello()
person.sayHello();
// 若有另一个子类则调用另一个子类的 sayHello()
Person person2 = Student2("Tom", 20, "xxSchool");
person2.sayHello();
```
# 相关