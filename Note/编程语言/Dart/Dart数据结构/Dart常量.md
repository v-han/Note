---
updated: 2026-10-17 19:22
created: 2026-10-17 19:07
tags:
---
# 介绍
**Dart**的**常量**，在定义之后无法修改。
# 使用方式
使用`const`关键字声明**常量**。
```dart
const pi = 3.14;
```

> [!NOTE]
> **const**定义的**常量**定义时不能使用在编译阶段无法确定的值，例如包含**变量**的值。
> ```dart
> const int a = 10;
> // 正确
> const int b = a + 1;
> 
> int x = 10;
> // 错误
> // const int c = x + 1;
> ```

使用`final`关键字声明一个**常量**，`final`声明的**常量**在运行阶段确定。
```dart
final time = DateTime.now();
```
# 相关