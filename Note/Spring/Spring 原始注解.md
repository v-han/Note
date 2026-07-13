---
updated: 2026-05-25 23:54
created: 2026-05-15 22:43
tags:
---
# 介绍
常用注解：
1. 作用在类上的
2. 作用在注入对象上的
3. 作用在方法上的

| 注解             | 说明                                   |
| -------------- | ------------------------------------ |
| @Component     | 使用在类上用于实例化Bean。                      |
| @Controller    | 使用在web层用于实例化Bean。                    |
| @Service       | 使用在service层上用于实例化Bean。               |
| @Repository    | 使用在dao层上用于实例化Bean。                   |
| @Autowired     | 使用在字段上用于根据类型依赖注入。                    |
| @Qualifier     | 结合@Autowired一起使用用于根据名称进行依赖注入。        |
| @Resource      | 相当于@Autowired + @Qualifier，按照名称进行注入。 |
| @Value         | 注入普通属性。                              |
| @Scope         | 标准Bean的作用范围。                         |
| @PostConstruct | 使用在方法上标注该方法是Bean的初始化方法。              |
| @PreDestory    | 使用在方法上标注该方法是Bean的销毁方法。               |

对于普通数据类型使用`@value`注解注入。
```java
@value("this is a string")
private String str;
```

对于引用数据类型可以通过`@Autowired`注解和`@Qualifier`注解注入。
```java
@Autowired
@Qualifier("userDao")
private UserDao userDao;
```

> [!NOTE]
> `@Qualifier`注解要配合`@Autowired`注解使用。
> 单个`@Autowired`注解是在Spring容器中根据数据类型匹配。
> 结合`@Qualifier`注解是在Spring容器中根据id匹配。

[[Spring 原始注解开发案例]]
# 相关