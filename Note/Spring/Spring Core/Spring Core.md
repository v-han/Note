---
updated: 2026-09-24 15:22
created: 2026-09-19 21:09
tags:
---

# 介绍
**Spring Core**是**Spring**中用来负责**对象的创建**、**管理和对象之间的依赖关系**的部分。主要由[[IoC]]和[[DI]]的方式完成。
# 使用方式
使用前需要导入相关的依赖。
```maven
<dependency>
	<groupId>org.springframework</groupId>
    <artifactId>spring-context</artifactId>
    <version>6.2.10</version>
</dependency>
```

配置一个[[Bean]]。

加载[[Spring应用上下文]]，使用**Spring应用上下文**获取对应的**Bean**。
```java
ApplicationContext app = new AnnotationConfigApplicationContext(SpringConfiguration.class);

UserDao userDao = app.get(UserDao.class);
```

> [!NOTE]
> 由于**注解**开发不需要麻烦的XML配置过程，这里推荐使用**注解**开发的方式。
# 相关
