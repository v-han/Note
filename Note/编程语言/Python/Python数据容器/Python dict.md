---
updated: 2026-08-20 09:56
created: 2026-08-09 17:53
tags:
---
# 介绍
**字典**(dict)是Python数据容器中的一种，其存储的是**键值对**(key: value)。
# 使用方式
使用`{}`将键值对包起来定义一个字典，然后赋值给一个变量。
```python
dict1 = {"num1": 1, "num2": 2}
```

> [!NOTE]
> 在**字典**中，**key**不可以重复(后面的会覆盖前面的)，而**value**可以重复。
> 且key**不能**为可变类型(列表、集合、字典等)，实际开发还是使用**字符串型**和**整型**较好。

使用`[]`对字典指定的**key**的**value**进行操作。
```python
# 将 "num1" key 对应的 value 取出。
num_out = dict1["num1"] 

# 将 "num_new" key 对应的 value 赋值 num_in
# 若没有 "num_new" 的 key 则会新增一个键值对。
dict1["num_new"] = num_in
```

使用`del`关键字删除指定key的键值对。
```python
# 删掉 key 为 "num_key" 的键值对。
del dict1["num_key"]
```

使用`in`关键字进行判断和遍历时实际上是对key的判断和遍历。
```python
# 判断 dict1 中有没有 "index" 的 key。
if "index" in dict1:

# 遍历 dict1 的所有key。
for i in dict1:
```
# 相关
[[Python dict常见方法]]