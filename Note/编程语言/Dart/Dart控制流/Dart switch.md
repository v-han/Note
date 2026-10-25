---
updated: 2026-10-19 17:00
created: 2026-10-19 15:57
tags:
---
# 介绍
**Dart**的分支控制流，使用`switch`和`case`进行条件判断，执行对应的分支。
# 使用方式
使用`switch`和`case`对条件进行判断，执行对应的分支。
```dart
int state = 1;

switch (state) {
	case 1:
		print("state 1");
		// dart switch 默认不会贯穿，可以不用 break
	cace 2:
	cace 3:
		// case 2 和 case 3 共享同一个逻辑
		ptint("other state");
	default:
		// 默认逻辑
		print("no state");
}
```

可以配合`when`进行更多的判断。
```dart
switch (score) {
	// 使用 n 接收 score 进行判断。
	case var n when n >= 80:
		print("good");
	// 也可以用表示简单的关系模式
	case >= 60:
		print("fine");
	// 其他情况略，多种 case 匹配方式可以混用
}
```

还可以使用`switch`表达式，`switch`表达式必须覆盖所有情况，且每种情况都需要一个表达式。可以使用`_`通配符接收其他情况。
```dart
int num = 1;

String numString = switch (num) {
	1 => "One",
	2 => "Two",
	<= 5 => "smaller than six",
	_ => "Other",
}
```


# 相关