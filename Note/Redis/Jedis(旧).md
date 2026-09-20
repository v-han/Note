---
updated: 2026-09-19 00:36
created: 2026-09-19 00:27
tags:
---
# 介绍
**Jedis**旧版的使用方式，此种方式是线程不安全的。
# 使用方式
引入相关的依赖。
```Maven
<dependency>
    <groupId>redis.clients</groupId>
    <artifactId>jedis</artifactId>
    <version>3.7.0</version>
</dependency>
```

建立**Redis**连接。
```java
// 建立连接
Jedis jedis = new Jedis("localhost", 6379);
// 设置密码
jedis.auth("123456");
// 选择数据库
jedis.select(0)；
```

执行对应的**Redis**操作，与新版操作一致。

释放连接。
```java
jedis.close()
```
# 相关
[[JedisPool]]