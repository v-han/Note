---
updated: 2026-09-19 00:28
created: 2026-09-18 23:26
tags:
---
# 介绍
**Jedis**是**Redis**的**Java**语言客户端。
# 使用方式
引入相关依赖。
```Maven
<dependency>
    <groupId>redis.clients</groupId>
    <artifactId>jedis</artifactId>
    <version>7.2.0</version>
</dependency>
```

连接**Redis**。
```java
// redis://用户名:密码@服务器地址:端口
RedisClient jedis = new RedisClient("redis://default:123456@localhost:6379");
```

执行对应的**Redis**操作，所有的操作和**Redis**的命令差不多。
```java
// 相当于执行 SET name Tom
jedis.set("name", "Tom");

// 相当于执行 GET name
String res = jedis.get("name");
```

执行完需要释放连接。
```java
jedis.close()
```
# 相关
[Redis提供的教程](https://redis.io/docs/latest/develop/clients/jedis/)
[[Jedis(旧)]]