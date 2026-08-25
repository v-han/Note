---
updated: 2026-08-21 21:24
created: 2026-08-21 21:23
tags:
---
# 介绍
**Python函数**的默认参数，在没传递指定的参数时会使用对应的默认值。
# 使用方式
在函数的参数中可以提供**默认参数**(也可以叫做**缺省参数**)，在调用函数时没提供对应的参数会使用定义函数时给出的默认值。
```python
def print_stu(name, age, class="class one"):
	print(f"name: { name }, age:{ age }, class:{ class }")

# 以下两种函数调用结果一样。
print_stu("Tom", 20)
print_stu("Tom", 20, "class one")
```

使用了默认参数之后不能再添加普通参数，即默认参数只能放在最后面。
```python
# 这种函数定义是不允许的。
def print_stu(name, age=20, class):
```
# 相关