---
updated: 2026-10-23 01:14
created: 2026-10-23 00:14
tags:
---
# 介绍
**Dart**中的**异常**(Exception)机制，用于处理程序运行过程中出现的错误。
# 使用方式
使用`throw`关键字抛出**异常**，可通过实现**Exception**接口自定义异常。
```dart
throw Exception("exception");
```

使用`try-catch`捕获并处理**异常**，还可以在后面添加`finally`代码块，其中的代码无论是否发生异常都会执行。
```dart
try {
	// 具体实现，在此处可以放可能发生异常的代码
} catch(e) {
	print(e);
	// 可以 catch(e, s) 得到异常堆栈信息
	// print(s);
} finally {
	// 无论是否发生异常都会执行，通常用于资源释放和清理操作
}
```

可以在`catch`中使用`rethrow`向上级抛出异常。
```dart
void main() {
	try {
		try {
			throw Exception("发生错误");
		} catch (e) {
		    print("捕获异常");
		    // 向上级的 catch 抛出异常
		    rethrow;
	    }
	} catch (e) {
	    print(e);
	}
}
```
# 相关