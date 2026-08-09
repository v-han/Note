---
updated: 2026-08-09 13:38
created: 2026-08-08 16:10
tags:
---
# 介绍
使用`if`进行条件分支流程控制。
# 使用方式
使用`if`对后面的条件表达式结果进行判断，到对应的分支执行对应的代码。
```python
if score > 60:
	print("good")
```

> [!NOTE]
> **Python**使用一个**缩进**来进行语句块的控制，表示代码的归属。
> 
> 不要忘记if语句后面的`:`。

可以配合`elif`和`else`实现多分支的分支控制。
```python
if score > 80:
	print("excellent")
elif score > 60:
	print("good")
else:
	print("bad")
```

> [!NOTE]
> 注意分支控制关键字`elif`和`else`的**缩进**。

可以使用`pass`关键字来进行语法占位，表示具体内容稍后再添加。
# 相关
当判断的表达式有一定的重复性，可以使用[[Python match|match]]。