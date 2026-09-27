---
updated: 2026-09-24 15:57
created: 2026-09-23 14:24
tags:
---
# 介绍
**Spring AOP**是**Spring**中用来实现[[AOP|面向切面编程]]的部分。
**Spring**原生的**AOP**是通过代理的方式进行的。
# 使用方式
使用前需要导入相关的依赖，这里与[[Spring Core]]的依赖一致。
```maven
<dependency>
	<groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>6.2.10</version>
</dependency>

<dependency>
    <groupId>org.aspectj</groupId>
    <artifactId>aspectjweaver</artifactId>
    <version>1.9.24</version>
</dependency>
```

配置[[Spring AOP配置|通知类]]。
# 相关