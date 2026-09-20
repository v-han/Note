---
updated: 2026-09-18 20:44
created: 2026-09-16 21:56
tags:
---
# 介绍
**Redis**中的**字符串**类型，是**Reids**中最简单的存储类型。
**Redis**的**字符串**又有以下三种类型**String**、**int**和**float**，底层都是字节数组形式存储的，只不过编码方式不同。存储的上限不能超过512M。
# 使用方式
使用`SET`为设置一个**字符串**类型的键值对。使用`MSET`来批量设置多个**字符串**类型的键值对。此外`SET`还有许多[[Redis SET选项|选项]]。
```redis
SET key value

MSET key value [key value ...]
```

使用`GET`获取指定**key**的**字符串**类型的**value**。使用`MGET`来批量根据**key**获取对应的**value**。
```redis
GET key

MGET key [key ...]
```

使用`INCR`让**key**的对应的**value**自增1，需要对有**int**型**value**的**key**使用。使用`INCRBY`能够使**value**按指定的步长自增。对于**float**型**value**，需要使用`INCRBYFLOAT`。
```redis
INCR key

INCRBY key increment

INCRBYFLOAT key increment
```

> [!NOTE]
> 这里**String**、**int**和**float**本质都是**字符串**类型，只是能对这三种类型进行不同的操作。
# 相关