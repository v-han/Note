---
updated: 2026-10-18 22:48
created: 2026-10-18 19:20
tags:
---
# 介绍
**Dart**中的**键值对类型**。
# 使用方式
使用`Map`关键字定义键值对类型，使用`{}`将内容包围。
```dart
Map ageMap = { "ageTom": 20 }
```

通过**key**可直接访问其的**value**。
```dart
ageMap["ageTom"] = 21;
```

使用`forEach`对**Map**进行遍历操作。
```dart
// 获取 key 和 value 并进行操作
ageMap.forEach((key, value) {
	// 具体操作
})
```

使用`addAll`在**Map**中添加**Map**。
```dart
ageMap.addAll({ "ageJack": 22 });
```

使用`containKey`判断**Map**中是否包含指定**key**。
```dart
bool res = ageMap.containKey("ageTom");
```

使用`remove`根据**key**删除对应的**键值对**。
```dart
age.remove("ageTom");
```
# 相关