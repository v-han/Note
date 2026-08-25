---
updated: 2026-08-19 13:55
created: 2026-08-19 09:57
tags:
---
# 介绍
**Python tuple**的[[组包与解包]]。
# 使用方式
使用`()`将元素括起来合成一个元组，这种操作称为**组包**。
```Python
num_tuple = (1, 2, 3)

# 不使用 () 直接罗列元素也是组包。
num_tuple = 1, 2, 3
```

直接用变量接收元组的元素，这种操作称为**解包**。
```Python
num_tuple = (1, 2, 3)
# a, b, c 分别接收到 1, 2, 3
a, b, c = num_tuple
```

> [!NOTE]
> 进行解包的时候记得变量数量和元素数量要一致。

在[[Python for|for]]循环中也能使用到解包。
```python
students = (
	("Tom", 20, 99),
	("Jack", 21, 98)
)
for name, age, score in students:
	print(f"{ name } { age } { score }")
```

使用`*`表示接收剩余元素，用于处理不确定数量元素的接收，以**列表**形式返回。
```python
num_tuple = (1, 2, 3, 4)

# x = 1, y = [2, 3, 4]
x, *y = num_tuple

# x = 1, y = [2, 3], z = 4
x, *y, z = num_tuple

# x = [1, 2, 3], y = 4
*x, y = num_tuple
```

> [!WARNING]
> 在解包的过程中，不允许使用两次`*`解包。
> ```python
> # 以下情况是不允许的
> x, *y, *z = (1, 2, 3, 4)
> ```

> [!TIPS]
> Python中两个变量的值交换也是使用了组包与解包。
> ```python
> # = 后面的在组包将 b, a -> (b, a)
> # = 前面的在解包
> a, b = b, a
> ```
# 相关