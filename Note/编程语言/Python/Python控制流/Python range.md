---
updated: 2026-08-12 10:29
created: 2026-08-11 22:43
tags:
---
# 介绍
使用`range`生成指定规则的数字序列，一般是**左开右闭**的。
# 使用方式
直接使用单个参数的`range(end)`生成一个从0开始到`end`结束的序列(不包括`end`)。
```python
# 生成的序列为 [0, 1, 2, 3]
range(4)
```

使用两个参数的`range(start, end)`表示从`start`到`end`结束的序列(不包括`end`)。
```python
# 生成的序列为 [1, 2, 3, 4]
range(1, 5)
```

使用三个参数的`range(start, end, step`表示从`start`到`end`结束的步长为`step`的序列(不包括`end`)。
```python
# 生成的序列为 [1, 3, 5]
range(1, 6, 2)
```
# 相关