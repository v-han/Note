---
updated: 2026-08-20 16:32
created: 2026-08-20 16:18
tags:
---
# 介绍
**Python函数**的说明文档(Docstring)，用于解释函数的功能、参数、返回值等信息。
# 使用方式
使用三个引号包裹字符串，放在函数定义下方。
```python
def num_add(a, b):
	"""
	this is function calculate a plus b
	:param a: 
	:param b: 
	:return: a plus b
	"""
	return a + b
```

`:param 参数:`用来解释参数。
`:return:`用来解释返回值。

使用`help()`函数来查看函数说明文档。
```python
# 这里传函数名，注意不要带上 ()，那是函数调用。
help(num_add)
```

> [!NOTE]
> 一般情况下**IDE**将指针悬浮在函数上就能看到函数说明文档。

# 相关