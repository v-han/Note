---
updated: 2026-08-09 13:47
created: 2026-08-08 22:40
tags:
---
# 介绍
使用`while`进行循环，使用**条件表达式**的判断进行循环控制。
# 使用方式
使用`while`对条件表达式进行判断，条件表达式成立执行循环内容。
```python
while num < 10:
	print(num)
	num += 1
```

`while`循环之后也可以加上`else`，表示循环结束后执行的代码。
```python
while num < 10:
	print(num)
	num += 1
else:
	print("Loop ends")
```

> [!NOTE]
> 使用`while`进行循环控制时要注意逻辑控制，不要变成死循环。
# 相关