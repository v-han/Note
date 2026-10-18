---
created: 2026-10-17 19:26
updated: 2026-10-17 19:38
tags:
---
# 介绍
**Dart**中的**字符串类型**。
# 使用方式
使用`String`定义**字符串**变量，使用`'`或`"`包含的字符串为其赋值。
```dart
String name = "Tom";
```

**Dart**的**字符串**支持**字符串插值**(String Interpolation)，可以使用`$`将**变量**或**表达式**嵌入**字符串**中。
```dart
String name = "Tom";
String message_name = "My name is $name";

// 对于表达式需要 {} 包起来
int age = 20;
String message_age = "next year I will be ${age + 1}";
```
# 相关


