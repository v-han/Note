---
updated: 2026-09-18 20:45
created: 2026-09-17 20:14
tags:
---
# 介绍
**Redis**的**Hash**数据类型。其可以将对象中的每个字段独立存储和操作，相较[[Redis String|String]]类型用字符串存储**JSON**的方式会更加灵活。
# 使用方式
**Hash**类型的**值**有两个部分**field**和**value**。

使用`HSET`来设置**key**的**field**的值。
```redis
HSET key field value [field value ...]
```

使用`HGET`获取一个指定**key**的指定**field**的**value**。使用`HMGET`获取一个指定**key**多个**field**的**value**。
```redis
HGET key field

HMGET key field [field ...]
```

使用`HGETALL`获取一个指定**key**的所有**field**和**value**。
```redis
HGETALL key
```

使用`HKEYS`和`HVALS`分别获取一个指定**key**的**field**和**value**。
```redis
HKEYS key

HVALS key
```

使用`HINCRBY`使一个指定**key**的指定**field**的**value**按指定步长自增。
```redis
HINCRBY key field increment
```

使用`HSETNX`来设置**key**的**field**的**value**，若已存在则不执行操作。
```
HSETNX key field value
```

使用`HSETEX`来设置**key**的**field**的**value**同时设置其的有效期。
# 相关