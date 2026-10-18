---
updated: 2026-10-17 20:14
created: 2026-10-17 19:39
tags:
---
# 介绍
**Dart**的**数字类型**，分为**num**(可整型可浮点)、**int**(整型)和**double**(浮点)。其中**num**是**int**和**double**的父类。
# 使用方式
使用`num`、`int`和`double`定义**数值型**变量。
```dart
num xNum = 111;
int xInt = 222;
double xDouble = 333;
```

三种类型之间基本不能**直接**转换。
```dart
// 大部分转换都是不允许的
// xInt = xNum;

// 除了 num 能接收 int 或 double 类型，因为 num 是他们父类
xNum = xInt;

// 需要一些方法来转换
xInt = xDouble.toInt();
```
# 相关