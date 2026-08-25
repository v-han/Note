---
updated: 2026-08-19 22:09
created: 2026-08-19 21:59
tags:
---
# 介绍
**Python dict**常见方法。
# 使用方式
使用`pop()`删除指定key对应的键值对。
```python
# 删掉 key 为 "dict_key" 对应的键值对。
# 作用和 del dict1["dict_key"] 相同。
dict1.pop("dict_key")
```

使用`get()`获取指定key对应的value。
```python
# 获取 key 为 "dict_key" 对应的 value。
# 作用和 dict1["dict_key"] 相同。
dict1.get("dict_key")
```

使用`keys()`获取字典中的所有key。
```python
dict1.keys()
```

使用`values()`获取字典中的所有value。
```python
dict1.values()
```

使用`items()`获取字典中的所有键值对。
```python
dict1.items()
```
# 相关