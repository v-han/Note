---
updated: 2026-08-19 13:56
created: 2026-08-13 15:47
tags:
---
# 介绍
**Python str**的常见方法。
# 使用方式
使用`find()`在字符串中查找子串，返回第一次出现的索引位置，若未找到返回`-1`。
```Python
# 返回值是 0
# 为了直观展示直接使用字面量，变量同理。
"string".find("str")
```

使用`count()`统计子串在字符串中出现的次数。
```python
# 返回值是 2，即出现了 2 次"str"。
"string is str type item".count("str")
```

使用`upper()`将字符串所有字母转化为大写。
```python
# "string" -> "STRING"
"string".upper()
```

使用`lower()`将字符串所有字母转化为小写。
```python
# "STRING" -> "string"
"STRING".lower()
```

使用`split()`将字符串按指定分割符分割成列表。
```python
# str_list = ["hello", "world", "python"]
str_list = "hello world python".split(" ")
```

使用`strip()`去除字符串两段的空白字符或指定字符。
```python
# " string " -> "string"
" string ".strip()

# "*string*" -> "string"
"*string*".strip("*")
```

使用`replace()`将字符串中的指定子串替换为其他子串。
```python
# "I am Tom" -> "I am Jack"
"I am Tom".replace("Tom", "Jack")
```

使用`startwith()`检查字符串是否以指定子串开头，此外还有`endwith()`检查是否以指定子串结尾。
```python
if "string".startwith("str"):
	print("string startwith str")
```

> [!NOTE]
> 以上的方法不会对原字符串进行操作，而是将结果返回。
# 相关