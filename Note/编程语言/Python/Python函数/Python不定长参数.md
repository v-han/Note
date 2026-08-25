---
updated: 2026-08-22 13:17
created: 2026-08-21 21:59
tags:
---
# 介绍
**Python函数**定义或调用时参数个数不确定时可以使用**不定长参数**(又叫**可变参数**)。
# 使用方式
使用`*`来使**位置传参**的参数接收不定长参数，本质上其实是[[Python tuple组包与解包|元组的解包]](此时的`args`类型是**元组**)。
```python
def my_max(*args):
	# 使用时直接使用 args。
	return max(args)

num_max = my_max(1, 2, 3, 4)
```

使用`**`来使**关键字传参**的参数接收不定长参数，这种方式传参会被封装为一个**字典**。
```python
def test_fun(**kwargs):
	# kwargs 是一个字典。
	# 保险起见在使用 kwargs 前最好判断一下对应的值是不是 None。
	print(kwargs["name"])
	
test_fun(name="Tom")
```

> [!NOTE]
> 这里`args`和`kwargs`(keywords args)都是约定俗成的，取其他名字也是可以的。
# 相关