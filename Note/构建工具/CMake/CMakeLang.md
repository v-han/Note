---
updated: 2026-08-18 19:18
created: 2026-08-18 18:33
tags:
---
# 介绍
CMake的一种语言**CMakeLang**(CMake Language)。
# 使用方式
**CMakeLang**仅有两种基本类型，分别是**字符串**和**列表**，而**列表**本质也是**字符串**，但使用`;`作为分隔符。
使用`set()`来给变量赋值。
```CMake
# 将变量 var 赋值 "World!"
set(var "World!")

# 变量 vars 是一个列表类型。
set(vars "word1;word2")
```

在使用的时候只需要使用`${}`花括号的方式来访问变量的值。
```CMake
# 使用 message() 打印指定字符串。 
message("Hello ${var}")
```

可以使用`list()`
> [!NOTE]
> 由于**CMakeLang**只有字符串，条件判断语句通过约定俗称的字符串进行判断，例如：
> `"True"`、`"On"`、`"Yes"`以及非零的数字(仍是字符串)来表示真。
> `"False"`、`"Off"`、`"No"`、`"0"`、`"Ignore"`、`"NotFound"`以及空字符串都被视为假。
> 尽管这样，还是尽量特定的一对字符串来表达。

# 相关