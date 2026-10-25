---
created: 2026-10-19 19:05
updated: 2026-10-19 19:09
tags:
---
# 介绍
**Dart**的循环控制流，使用`for`可以通过循环变量控制循环次数，也可以遍历集合中的元素。
# 使用方式
使用`for`可以实现指定次数的循环。
```dart
for (int i = 0;i < 10;i++) {
	print(i);
}
```

使用`for`还可以实现集合的遍历。
```dart
List<String> names = ["Tom", "Jack"];

for (name in names) {
	print(name);
}
```

可以使用`break`和`continue`控制循环。
# 相关