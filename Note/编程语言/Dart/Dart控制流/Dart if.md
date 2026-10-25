---
created: 2026-10-19 15:43
updated: 2026-10-19 15:56
tags:
---
# 介绍
**Dart**的分支控制流，使用`if`进行条件判断，执行对应的分支。
# 使用方式
和其他语言一样可以用`if`、`else if`和`else`进行条件控制。
```dart
if (score > 80) {
	print("good");
} else if (score > 60) {
	print("fine");
} else {
	print("bad");
}
```

可以和C语言一样使用**三元运算符**进行简单的分支判断。
```dart
// 对 isTom 判断，若是 true 则 name 为 Tom
String name = isTom ? "Tom" : "not Tom";
```
# 相关