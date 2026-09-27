---
updated: 2026-09-24 23:37
created: 2026-09-24 15:57
tags:
---
# 介绍
**Spring AOP**的**切入点表达式**，用于描述**切入点**。
# 使用方式
使用`execution`按照方法来匹配切入点。
```java
// 匹配
@Pointcut(execution(public void org.example.dao.UserDao.updata()))
```

使用`within`按照包和类来匹配切入点。
使用`this`按照代理对象的类型来匹配切入点。
使用`target`按照目标对象的类型来匹配切入点。
使用`args`按照方法参数来匹配切入点。
使用`@target`按照目标对象的注解来匹配切入点。
使用`@args`按照方法参数的注解来匹配切入点。
使用`@within`按照类的注解来匹配切入点。
使用`@annotation`按照方法的注解来匹配切入点。
# 相关