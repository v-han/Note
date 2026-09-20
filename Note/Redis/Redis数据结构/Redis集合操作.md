---
updated: 2026-09-18 20:41
created: 2026-09-18 16:07
tags:
---
# 介绍
**Redis**的**集合**的操作，包含**交、差、并**操作。
# 使用方式
使用`SINTER`获取多个指定**key**的**Set**的交集。
```redis
SINTER key [key ...]
```

使用`SDIFF`获取多个指定**key**的**Set**的差集(第一个集合有，后面的集合都没有的元素的集合)。
```redis
SDIFF key [key ...]
```

使用`SUNION`获取多个指定**key**的**Set**的并集。
```redis
SUNION key [key ...]
```
# 相关