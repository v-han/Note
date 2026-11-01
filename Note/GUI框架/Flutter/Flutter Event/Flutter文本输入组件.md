---
updated: 2026-10-26 20:09
created: 2026-10-26 18:39
tags:
---
# 介绍
**Flutter**提供了多种内置的**文本输入组件**，用于接收和处理用户输入的文本内容。
# 使用方式
**Flutter**中有以下常见的**文本输入组件**：**TextField**、**TextFormField** 和 **SearchBar**。

通过为**文本输入组件**的事件属性设置**匿名函数**，注册对应事件的**回调函数**。还可以设置**decoration**装饰器来控制文本框的样式。
```dart
TextField(
	onChanged: (value) {
	    print("输入内容：$value");
	},
	decoration: InputDecoration(
	    labelText: "用户名",
	    hintText: "请输入用户名",
	    prefixIcon: Icon(Icons.person),
	    border: OutlineInputBorder(),
	),
)
```

**TextFormField**是**Flutter**提供的表单文本输入组件，在**TextField**的基础上增加了**表单验证**、**保存**和**重置**等功能，通常配合**Form**组件使用。
```dart
validator: (value) {
  if (value == null || value.isEmpty) {
    return "用户名不能为空";
  }
  return null;
},
```
# 相关