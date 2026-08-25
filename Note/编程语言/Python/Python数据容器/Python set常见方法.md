---
updated: 2026-08-19 21:15
created: 2026-08-19 17:46
tags:
---
# 介绍
**Python set**的常见方法。
# 使用方式
使用`add()`添加元素到集合中。
```python
num_set.add(1)
```

使用`remove()`移除指定元素，找不到指定元素则报错。
```python
num_set.remove(1)
```

使用`pop()`随机删除集合中的元素并返回。
```python
num1 = num_set.pop()
```

使用`clear()`清空集合。
```python
num_set.clear()
```

使用`difference()`求两个集合的差集。
```python
# 返回 num_set 有但 num_set2 没有的集合。
num_set.difference(num_set2)
```

使用`union()`求两个集合的并集。
```python
# 返回 num_set 和 num_set2 的并集。
num_set.union(num_set2)
```

使用`intersection()`求两个集合的交集。
```python
# 返回 num_set 和 num_set2 的交集。
num_set.intersection(num_set2)
```

> [!NOTE]
> 集合也可以使用`&`、`-`、`|`分别进行集合的交、差、并操作。
# 相关