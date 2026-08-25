---
updated: 2026-08-22 10:55
created: 2026-08-21 17:52
tags:
---
# 介绍
Python使用函数的参数，供函数内部使用。
# 使用方式
出了传递正常的参数，Python的参数还能传递函数。
```python
def num_add(a, b):
	return a + b
	
def test_fun(a, b, oper):
	return oper(a, b)

test_fun(1, 2, num_add)
```
# 相关
[[Python传参方式]]
[[Python默认参数]]
[[Python不定长参数]]
[[Python类型注解]]