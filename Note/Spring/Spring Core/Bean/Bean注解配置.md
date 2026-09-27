---
updated: 2026-09-23 13:55
created: 2026-09-21 21:10
tags:
---
# 介绍
使用**注解**的方式配置**Bean**，使用这种方式来配置**Bean**还需要配置[[组件扫描]]。
# 使用方式
将以下注解作用在类上，可以将该类交由**Spring IoC容器**管理，使其成为**Spring**中的**Bean**。常见的注解包括`@Component`(表示通用组件)、`@Service`(表示业务层组件)、`@Repository`(表示持久层组件)和`@Controller`(表示控制层组件)。
```java
// 表示创建一个 id 为 userDao 的 Bean
@Component("userDao")
public class UserDaoImpl implements UserDao {
	// 内部代码略
}
```

使用`@Scope`注解来配置Bean的[[Bean Scope|作用范围]]。
```java
// 表示创建一个 id 为 userDao 的 Bean
@Component("userDao")
@Scope("singleton")
public class UserDaoImpl implements UserDao {
	// 内部代码略
}
```

使用`@PostConstruct`和`@PreDestory`注解作用在类的方法上分别表示**Bean**的**初始化方法**和**销毁方法**。
# 相关
使用[[Bean依赖注入注解配置|注解]]的方式为**Bean**配置所需注入的依赖。
[[第三方类Bean注解配置]]