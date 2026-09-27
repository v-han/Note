---
updated: 2026-09-22 21:26
created: 2026-09-21 23:07
tags:
---
# 介绍
使用**注解**的方式为**Bean**配置所需注入的依赖。
# 使用方式
使用`@Value`为**Bean**注入普通数据类型。
```java
@Value("Tom")
private String username;
```

使用`@Autowire`(自动装配)为**Bean**注入引用数据类型(即**Bean**)。直接使用`@Autowire`会按照**类型**进行匹配。
```java
// 使用在属性上
@Autowire
private UserDao userDao;

// 使用在 set 方法上
@Autowired
public void setUserDao(UserDao userDao) {
	this.userDao = userDao;
}

// 使用在构造方法上
@Autowired
public UserService(UserDao userDao) {
	this.userDao = userDao;
}
```

若出现多个类型相同的**Bean**时，`@Autowire`需配合`@Qualifier`根据**Bean**的**id**进行匹配。
```java
// 注入 id 为 userDao 的 Bean
@Autowire
@Qualifier("userDao")
private UserDao userDao;

// 使用在 set 方法和构造方法上的略
```
# 相关