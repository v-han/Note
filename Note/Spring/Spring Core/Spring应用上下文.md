---
updated: 2026-09-23 13:43
created: 2026-09-20 00:37
tags:
---
# 介绍
**String**的**应用上下文**(ApplicationContext)，是Spring提供的[[IoC|IoC容器]]，用来**创建**、**管理**和**获取Bean**。
# 使用方式
`ApplicationContext`是个接口类，其有3个实现类：
1. `ClassPathXmlApplicationContext`：从类的根路径加载[[Spring应用上下文XML配置|XML配置文件]]。
2. `FileSystemXmlApplicationContext`：从磁盘路径上加载**XML配置文件**。
3. `AnnotationConfigApplicationContext`：使用[[Spring应用上下文注解配置|注解]]的方式来配置**IoC容器**。

创建一个`ApplicationContext`对象。
```java
// 使用 XML 配置文件创建应用上下文
ApplicationContext app = new ClassPathXmlApplicationContext("applicationContext.xml");

// 使用注解的方式读取 Spring 配置文件创建应用上下文
ApplicationContext app = new AnnotationConfigApplicationContext(SpringConfiguration.class);
```

使用以下两个方法获取**Spring IoC容器**中的**Bean**。
```java
// 此方法使用 id 获取 Bean，返回 Object 类，需要类型转换
public Object getBean(String name) throws BeansException

// 此方法使用类获取 Bean，直接放回 Bean，无需类型转换
public <T> T getBean(Class<T> requiredType) throws BeansException
```
# 相关