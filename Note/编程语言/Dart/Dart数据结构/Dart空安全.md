---
updated: 2026-10-19 00:50
created: 2026-10-19 00:33
tags:
---
# 介绍
**Dart**的**空安全**(Null Safety)是一种用于避免空引用错误的机制。在编译阶段检查变量是否可能为`null`，从而减少程序运行时因空值访问而产生的错误。
# 使用方式
使用`?`表示该变量可空。
```dart
String? name = null;
// 以下代码是不允许的
// String name = null;
```

使用`?.`进行安全访问。
```dart
// 若 name 的值为 null，直接返回 null
name?.startsWith("1");
```

使用`!.`进行非空断言，由开发者确定变量非空。
```dart
// 若 name 为空，程序能通过编译，但在运行时崩溃
name!.startsWith("1");
```

使用`??`进行空合并，可以提供默认值。
```dart
// 当 name 为空时，使用 "host"
String hostName = name ?? "host";

// 若 name 为空时，为其赋值 "host"
name ??= "host";
```
# 相关