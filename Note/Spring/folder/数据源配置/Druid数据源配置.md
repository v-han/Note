---
updated: 2026-05-25 23:46
created: 2026-05-14 21:34
tags:
---
# 开发步骤
导入数据源的坐标和数据库驱动坐标。
```Maven
<!-- mysql jdbc驱动 -->
<dependency>  
    <groupId>com.mysql</groupId>  
    <artifactId>mysql-connector-j</artifactId>  
    <version>9.6.0</version>  
</dependency>

<!-- Druid数据源 -->
<dependency>
	<groupId>com.alibaba</groupId>
	<artifactId>druid</artifactId>
	<version>1.1.10</version>
</dependency>
```

普通方法创建数据源对象。

创建数据源Bean对象。[[依赖注入的基本配置|导入properties文件]]
```XML
<bean id="dataSource" class="com.alibaba.druid.pool.DruidDataSource">
	<property name="driverClassName" value="${mysql.driver}"></property>  
    <property name="url" value="${mysql.url}"></property>  
    <property name="username" value="${mysql.username}"></property>  
    <property name="password" value="${mysql.password}"></property> 
</bean>
```
# 相关