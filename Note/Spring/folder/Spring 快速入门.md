---
updated: 2026-06-01 23:01
created: 2026-04-16 23:45
tags:
---
# 传统开发步骤
```java
UserDao userDao = new UserDaoImpl();
```
# Spring 开发步骤
在Maven中导入对应的包：
```Maven
<dependency>
	<groupId>org.springframework</groupId>
	<artifactId>spring-context</artifactId>
	<version>5.0.5.RELEASE</version>
</dependency>
```

创建一个接口：
```java
package org.example.dao;  
  
public interface UserDao {  
    public void methon();  
}
```

创建一个接口的实现类：
```java
package org.example.dao.impl;

import org.example.dao.UserDao;

public class UserDaoImpl implements UserDao {
	public void methon() {
		System.out.println("this is a methon");
	}
}
```

在resources目录下创建一个`applicationContext.xml`(叫什么都行，只不过约定俗成叫这个)。[[依赖注入的基本配置|applicationContext的一些配置]]。
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<beans xmlns="http://www.springframework.org/schema/beans"  
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans    http://www.springframework.org/schema/beans/spring-beans.xsd">  
  
  <bean id="userDao" class="org.example.dao.impl.UserDaoImpl"></bean>
  
</beans>
```

要使用Bean对象时：
```java
package org.example.demo;  
  
import org.example.dao.UserDao;  
import org.springframework.context.ApplicationContext;  
import org.springframework.context.support.ClassPathXmlApplicationContext;  
  
public class UserDaoDemo {  
    public static void main(String[] args) {  
       ApplicationContext app = new ClassPathXmlApplicationContext("applicationContext.xml");  
       UserDao userDao = (UserDao) app.getBean("userDao");  
       userDao.methon();  
    }  
}
```


> [!NOTE]
> 这里`getBean()`方法使用Bean的id时需要类型转换。使用类输入时不需要，例如：`getBean(UserDao.class)`。

# 相关