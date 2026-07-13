---
updated: 2026-05-15 22:38
created: 2026-04-25 01:20
tags:
---
# ApplicationContext接口
`ApplicationContext`：接口类型，其有3个实现类：
1. `ClassPathXmlApplicationContext`：从类的根路径加载配置文件。
2. `FileSystemXmlApplicationContext`：从磁盘路径上加载配置文件。参数为配置文件的磁盘路径。
3. `AnnotationConfigApplicationContext`：使用注解配置容器对象时需要用此类创建spring容器。用来读取注解。
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