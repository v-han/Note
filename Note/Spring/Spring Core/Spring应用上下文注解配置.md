---
updated: 2026-09-23 14:09
created: 2026-09-21 21:14
tags:
---
# 介绍
使用**注解**方式配置**Spring**的**应用上下文**(ApplicationContext)。
# 使用方式
使用以下的注解配置**Spring应用上下文配置**类。
```java
// 表示当前类是 Spring 应用上下文配置类
@Configuration
// 组件扫描，扫描 org.example 包下的组件
@ComponentScan("org.example")
// 加载类加载路径下的 db.properties 配置文件
@PropertySource("classpath:db.properties")
// 导入 DBconfig.class 
@Import(DBConfig.class)
public class SpringConfiguration {}
```

`@Configuration`：表示当前类是一个**Spring配置类**。   
`@ComponentScan`：配置[[组件扫描]]的范围。
`@PropertySource`：配置需要加载的`.properties`**配置文件**，可以使用`@Value("${}")`的形式取到**配置文件**中的值。
`@Import`：导入其他**配置类或指定的Bean**。

> [!NOTE]
> `@PropertySource`和`@Import`导入多个文件或类时，可以使用`{}`括起来，例如`@Import({DBConfig.class, MyConfig.class})`。
# 相关