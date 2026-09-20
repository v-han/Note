---
updated: 2026-09-18 20:39
created: 2026-09-18 00:15
tags:
---
# 介绍
**Redis**中的**列表类型**。与**链表**的功能较为相似，**有序**、**插入和删除快**。
# 使用方式
使用`LPUSH`和`RPUSH`分别在指定的**key**对应的**List**左侧或右侧插入一个或多个元素，按给出的顺序插入。
```redis
LPUSH key element [element ...]

RPUSH key element [element ...]
```

使用`LPOP`和`RPOP`分别在指定的**key**对应的**List**左侧或右侧移除指定个数(默认是1个)元素并返回。使用`BLPOP`和`RLPOP`在没有元素时等待一段时间而不是立即返回**nil**。
```redis
LPOP key [count]

# 使用 BLPOP 若没有元素则阻塞 timeout 时间
# 等到有元素时在移除并返回，若仍没有元素则返回 nil
BLPOP key [key ...] timeout
```

使用`LRANGE`来获取指定的**key**对应的**List**指定下标(从0开始)的所有元素。
```redis
LRANGE key start stop
```
# 相关