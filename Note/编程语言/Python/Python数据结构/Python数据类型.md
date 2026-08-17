---
updated: 2026-08-13 15:41
created: 2026-08-08 12:12
tags:
---
# 介绍
**Python**的数据类型。
# 数据类型
1. 数字类型：
	1. 整型(int)即整数，例如`1`。
	2. 浮点型(float)即小数，例如`3.14`。
2. 布尔型：bool，例如`True`和`False`(开头大写)，在数学运算中分别为**1**和**0**。
3. [[Python str|字符串型]]。
4. 空值：NoneType，仅包含一个`None`。
5. 数据容器：存储多项数据的容器，[[Python list|列表]]、[[Python tuple|元组]]、[[Python set|集合]]和[[Python dict|字典]]等。

可以使用`type()`函数查看得到的数据类型。
```python
# 通过字面量查看数据类型
print(type("hello"))

# 通过变量查看数据类型
str = "hello"
print(type(str))
```

可以使用`isinstance()`函数检查是否是指定的数据类型，返回值是一个**bool**类型。
```python
flag = True
print(isinstance(flag, bool))
```
# 相关