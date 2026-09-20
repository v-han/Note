---
updated: 2026-09-16 21:55
created: 2026-09-16 21:43
tags:
---
# 介绍
**Redis**的通用命令。
# 使用方式
使用`KEYS`查看符合模板的所有**key**。由于该命令查看所有的**key**会消耗大量时间，在生产环境谨慎使用。
```redis
# 查看符合 a* 模板的 key
KEYS a*
```

使用`DEL`删除一个指定的**key**，并返回成功删除的**key**数。
```reids
# 删除 k1 k2 的 key
DEL k1 k2
```

使用`EXISTS`判断**key**是否存在，存在返回1不存在返回0。
```redis
# 判断 k1 的 key 是否存在
EXISTS k1
```

使用`EXPIRE`给**key**设置有效期，到期时**key**会被自动删除。此外使用`TTL`查看**key**的有效期(`-1`表示永久有效，`-2`表示过期)。
```reids
# 给 k1 的 key 设置 20s 的有效期
EXPIRE k1 20

# 查看 k1 的 key 的有效期
TTL k1
```
# 相关