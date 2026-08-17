---
updated: 2026-08-13 17:23
created: 2026-08-09 17:53
tags:
---
# 介绍
**字符串**(str)是Python数据容器中的一种[[序列类型]]，可以一次性存储多个字符元素。
字符串**元素有序**且具有**不可变性**。
# 使用方式
可以使用单引号，双引号来定义字符串。
```python
str1 = 'String1'
str2 = "String2"
```

当需要使用多行的字符串时，需要使用三引号(三个双引号)方式定义。
```python
str3 = """
	this is first line.
	this is second line.
	this is third line.
"""
```

> [!NOTE]
> 当字符串中出现一些特殊字符时可以使用转移字符。

可以通过[[Python索引|索引]]进行操作，但字符串的元素无法改变。
```python
# 这种方式是不被允许的。
string[1] = 'a'

# 这种方式是允许的。
char = string[1]
```

和**列表**一样，使用`in`关键字判断**元素**或**字符串**是否在字符串中。
```python
if "s" in "str":
	print("s is in the word str")

if "str" in "string":
	print("str is in the word string")
```
# 相关
[[Python字符串拼接|字符串拼接]]
[[Python字符串格式化|字符串格式化]]
[[Python str常见方法]]
