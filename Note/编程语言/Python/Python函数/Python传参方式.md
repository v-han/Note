---
updated: 2026-08-21 21:01
created: 2026-08-21 20:57
tags:
---
# 介绍
**Python函数**的传参方式。
# 使用方式
**位置传参**：根据函数定义时的位置来传递参数，在调用函数时参数的顺序与定义函数时的顺序一致。这种传参方式比较简洁，但可读性较差。
```python
def print_stu(name, age, class)
	print(f"name: { name }, age:{ age }, class:{ class }")
	
print_stu("Tom", 20, "class one")
```

**关键字传参**：在调用函数时，参数以赋值的形式传递，这种传参方式不要求传参的顺序。这种传参方式比较繁琐，但可读性强。
```python

print_stu(name="Tom", class="class one", age=20)
```

两种传参方式可以混合使用，**但是**使用了**关键字传参**之后不能再用**位置传参**。
```python
# 这种方式是可以的。
print_stu("Tom", class="class one", age=20)

# 这种方式是不允许的。
print_stu(name="Tom", 20, "class one")
```
# 相关