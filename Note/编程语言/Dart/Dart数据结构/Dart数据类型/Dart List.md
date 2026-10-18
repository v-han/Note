---
created: 2026-10-17 23:21
updated: 2026-10-18 19:25
tags:
---
# 介绍
**Dart**的**列表类型**，用于存储多个元素。
# 使用方式
使用`List`关键字来定义一个**列表**，使用`[]`包围。
```dart
// List 可以存储多种类型的元素
List list = [1, "2", 3.0];
// 与下面写法等效，表示动态类型
List<dynamic> list = [1, "2", 3.0];
```

使用`<类型>`来指定**列表元素**的类型。
```dart
List<int> listInt = [1, 2, 3];
```

和其他语言一样，能够通过索引访问对应元素。
```dart
int res = list[1];
```

使用`add`和`addAll`方法在**列表**尾部添加元素。
```dart
// 添加元素
list.add(1);
// 添加一个列表，将 1, 2 添加到列表尾部
list.addAll([1, 2]);
```

使用`remove`等方法删除**列表**中的元素。
```dart
// 根据内容删除，删除列表中第一个 1 元素
list.remove(1);
// 根据索引删除，删除索引为 1 的元素
list.removeAt(1);
// 删除最后一个元素
list.removeLast();
// 根据索引删除左开右闭，这里只删除索引为 1 的元素
list.removeRange(1, 2);
```

使用`forEach`、`every`和`where`等对**列表**进行遍历、判断和筛选操作，传入一个**匿名函数**对元素进行操作及判断。
```dart
// 使用 forEach 对列表元素进行统一操作
list.forEach((item) { print(item); })

// 使用 every 判断是否所有元素都满足条件
bool result = list.every((item) => item > 0);

// 使用 where 筛选元素，返回类型是 Iterable，需要类型转换
List result2 = list.where((item) => item > 0).toList();
```
# 相关