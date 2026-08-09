---
updated: 2026-08-08 15:51
created: 2026-08-08 15:39
tags:
---
# 介绍
**Python**的输入输出，获取控制台输入输出。
# 使用方式
使用`input()`获取输入。
```python
name = input("please input:")
```

这样会在控制台中函数内指定文本之后亮出光标获取输入(以回车结束)。

> [!NOTE]
> 无论键盘输入的是什么类型，获取到的数据都是**字符串类型**。

使用`print()`函数输出。
```python
print(f"Your name is { name }")
```
# 相关