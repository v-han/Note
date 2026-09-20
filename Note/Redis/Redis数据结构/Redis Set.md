---
updated: 2026-09-18 20:41
created: 2026-09-18 00:55
tags:
---
# 介绍
**Redis**中的**集合类型**，**无序**、**元素不可重复**。
# 使用方式
使用`SADD`向指定的**key**的**Set**中添加一个或多个元素。
```redis
SADD key member [member ...]
```

使用`SREM`移除指定**key**的**Set**中的指定元素。
```redis
SREM key member [member ...]
```

使用`SCARD`获取指定**key**的**Set**中的元素个数。使用`SMEMBERS`获取指定key的Set中的所有元素。
```redis
SCARD key

SMEMBERS key
```

使用`SISMEMBER`判断一个元素是否是在指定**key**的**Set**中。
```redis
SISMEMBER key member
```
# 相关
[[Redis集合操作]]