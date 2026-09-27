---
updated: 2026-09-23 14:03
created: 2026-09-23 13:55
tags:
---
# 介绍
第三方类的**Bean**注解配置。
# 使用方式
在方法上使用`@Bean`注解，表示此方法的返回值以**Bean**的形式由**Spring IoC容器**管理。可以使用这种方式利用注解配置第三方类的**Bean**。
```java
@Bean
public DataSource dataSource() {
	DruidDataSource ds = new DruidDataSource();
	ds.setDriverClassName(driver);
	ds.setUrl(url);
	ds.setUsername(username);
	ds.setPassword(password);
	return ds;
}
```

若需要依赖注入，可以在方法的参数中添加，**Spring IoC容器**会为其根据类型**自动装配**。
```java
@Bean
public DataSource dataSource(UserDao userDao) {
	// 代码略
}

// 若有重复类型的，可以使用 @Qualifier 根据 id 自动装配
@Bean
public DataSource dataSource(
	@Qualifier("userDao1") UserDao userDao) {
	// 代码略
}
```
# 相关