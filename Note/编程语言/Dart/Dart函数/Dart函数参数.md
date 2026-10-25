---
updated: 2026-10-19 22:29
created: 2026-10-19 20:53
tags:
---
# 介绍
**Dart**中函数的**参数**，分为**必需位置参数**(Required Positional)、**可选位置参数**(Optional Positional)和**命名参数**(Named)。
# 使用方式
**必需位置参数**在函数定义中声明，需要按**指定位置**和**顺序**传入。
```dart
void sayHello(String name, int age) {
  print("$name is $age years old");
}

sayHello("Tom", 20);
```

**可选位置参数**在函数定义中用`[]`包起来，必须放在**必需位置参数**之后，不能与**命名参数**同时使用。使用默认值时需要注意[[Dart空安全|空安全]]。
```dart
// 可选位置参数可以提供默认值
// 不给出且不传入默认是 null，注意空安全机制
void sayHello(String name, [int age = 18]) {
  print("$name is $age years old");
}

// 传递参数时仍要注意顺序
sayHello("Tom");
sayHello("Tom", 20);
```

**命名参数**在函数定义中用`{}`包起来，可以单独使用，也可以与必需位置参数同时使用。如果同时使用，**命名参数**必须放在**必需位置参数**之后。
```dart
// 使用 required 表示该参数必传，使用默认值也要主要空安全
void sayHello({required String name, int age = 18}) {
  print("$name is $age years old");
}

// 若有 必需位置参数 先写 必需位置参数
// sayHello(必需位置参数, name: "Tom");
// 调用函数时通过参数名称传递使用 (参数: 值) 的方式传递
sayHello(name: "Tom");
```
# 相关