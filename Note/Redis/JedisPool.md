---
updated: 2026-09-19 00:47
created: 2026-09-19 00:37
tags:
---
# 介绍
**Jedis**(旧)是线程不安全的，并且频繁的创建和销毁连接会有性能损失。因此需要**Jedis**连接池来代替直连的方式。
# 使用方式
创建一个连接池配置。
```java
JedisPoolConfig poolConfig = new JedisPoolConfig();

// 设置最大连接数，其余的配置省略
poolConfig.setMaxTotal(8);
```

使用连接池配置创建连接池对象。
```java
JedisPool jedisPool = new JedisPool(poolConfig, "localhost", 6379, 1000, "123456");
```

使用连接池获取Jedis对象。
```java
Jedis jedis = jedisPool.getResource();

// 使用完归还连接对象
jedis.close()
```
# 相关