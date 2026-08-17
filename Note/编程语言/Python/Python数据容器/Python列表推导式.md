---
updated: 2026-08-13 10:51
created: 2026-08-13 10:46
tags:
---
# 介绍
使用列表推导式可以使列表的生成更加方便。
# 使用方式
使用`[表达式 for语句]`的形式生成列表。
```python
# num_list = [2, 4, 6]
num_list = [i * 2 for i in range(1, 4)]
```

使用加上`if`的推导式加上判断条件。
```python
# num_list = [4, 8]
num_list = [i * 2 for i in range(1, 6) if i % 2 == 0]
```
# 相关