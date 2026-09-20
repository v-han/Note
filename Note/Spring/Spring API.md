---
updated: 2026-09-20 00:41
created: 2026-04-25 01:20
tags:
---
# ApplicationContext接口

# getBean方法
`getBean()`方法有两个方法实现(实现代码略)：
```java
public Object getBean(String name) throws BeansException
public <T> T getBean(Class<T> requiredType) throws BeansException
```

1. 通过字符串(Bean的id)的方式。
```java
UserDao userDao = (UserDao) app.getBean("userDao");
```

> [!NOTE] 
> 这种方法需要强制类型转换。
> 且允许某个类型有多个Bean(id不同，但类相同，并在XML文件中配置)。

2. 通过字节码的方式。
```java
UserDao userDao = app.getBean(UserDao.class)
```

> [!NOTE]
> 这种方法不需要强制类型转换。
> 同个类只能创建一个Bean对象。
# 相关
上一篇：[[Spring 配置文件]]
下一篇：[[Spring 配置数据源]]