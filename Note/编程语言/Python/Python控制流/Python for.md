---
updated: 2026-08-19 13:49
created: 2026-08-09 13:42
tags:
---
# 介绍
使用`for`进行循环，使用**轮询遍历**的方式进行循环控制。
# 使用方式
使用`for`从待处理的数据集中取出元素，进行循环。
```python
# for 元素 in 待处理的数据集:
for i in range(1, 4):
	print(i)
	
# 以列表为例，遍历其中的元素
for item in list1:
	print(item)
```

在`for`循环之后也可以加上`else`，表示循环结束之后要执行的程序。
```python
for i in range(1, 4):
	print(i)
else:
	print("Loop ends")
```
# 相关
与`for`配合使用较多的[[Python range|range]]。