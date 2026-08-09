---
updated: 2026-08-08 22:39
created: 2026-08-08 22:23
tags:
---
# 介绍
使用`match`进行**模式匹配**。使用一个模板匹配数据结构和内容，匹配成功则执行对应的代码。

> [!NOTE]
> `match`是Python3.10加入的功能。
# 使用方式
使用`match`和`case`结合进行模式匹配。
```python
match day:
	case "1":
		print("Monday")
	case "2":
		print("Tuesday")
	case "3":
		print("Wednesday")
	case "4":
		print("Thursday")
	case "5":
		print("Friday")
	case "6" | "7":
		# | 表示匹配多项
		print("Weekend")
	case _:
		# 匹配其他情况
		print("Type Error")
```

当有一个模式匹配上时，之后的同一级的匹配分支都将略过。
# 相关
[[Python if|if语句]]更适合**复杂逻辑**和**范围匹配**等情况