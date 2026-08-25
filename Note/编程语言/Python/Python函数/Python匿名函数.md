---
updated: 2026-08-22 10:54
created: 2026-08-21 22:37
tags:
---
# 介绍
**匿名函数**指的是没有名字的函数，而正常的函数都是有名字的。
# 使用方式
使用`lambda 参数列表 : 函数体`的方式来声明**匿名函数**。
```python
lambda : print("this is a lambda functon")

# lambda 不需要 return 会将表达式返回。
lambda x, y : x + y
```

由于**匿名函数**没有名字，使用时要将其赋值给一个变量。
```python
add = lambda x, y : x + y

add(100, 200)
```

> [!NOTE]
> **匿名函数**(lambda表达式)只能有一个表达式，所以只能写简单的表达式或单行的语句。加上匿名的特定，通常用于给高阶函数传参。
> ```python
> stus = [
> 	("Tom", 20),
> 	("Jack", 30),
> 	("Name", 21)
> ]
> # 根据年龄进行排序，lambda 提供排序逻辑。
> stus.sort(key=lambda x : x[1])
> ```
# 相关