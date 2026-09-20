---
updated: 2026-09-18 21:35
created: 2026-09-18 17:24
tags:
---
# 介绍
**Redis**中的**可排序**的**集合类型**，**无序**、**元素不可重复**。
# 使用方式
使用**SortedSet**时，每个元素带有一个**score**，按给出的**score**进行排序。

使用`ZADD`向指定**key**的**SortedSet**添加一个或多个元素。
```redis
ZADD key score menber
```

使用`ZREM`删除指定**key**的**SortedSet**的一个指定元素。
```redis
ZREM key member [member ...]
```

使用`ZSCORE`获取指定**key**的**SortedSet**的指定元素的score值。使用`ZRANK`获取指定**key**的**SortedSet**的指定元素的排名(索引)。
```redis
ZSCORE key member

# WITHSCORE 选项表示同时返回 score
ZRANK key member [WITHSCORE]
```

使用`ZCARD`获取指定**key**的**SortedSet**的元素个数。使用`ZCOUNT`获取指定**key**的**SortedSet**的指定**score**区间中的元素个数。
```redis
ZCARD key

ZCOUNT key min max
```

使用`ZINCRBY`将指定**key**的**SortedSet**和指定元素按指定步长自增。
```redis
ZINCRBY key increment member
```

使用`ZRANGE`获取指定**key**的**SortedSet**的指定**score**区间的元素(按**score**排序)。
```redis
# BYSCORE BYLEX 分别表示用 score 和 索引 表示区间
# REV 表示从高到低排序
# LIMIT offset count 表示跳过开头多少个和输出多少个元素
ZRANGE key start stop [BYSCORE | BYLEX] [REV] [LIMIT offset count] [WITHSCORES]
```
# 相关
**SortedSet**的**交、差、并**集[[Redis集合操作|操作]]分别为`ZINTER`、`ZDIFF`、`ZUNION`。