---
updated: 2026-05-25 22:50
created: 2026-05-16 23:13
tags:
---
# 开发步骤
创建一个dao层接口：
```java
package org.example.dao;  
  
public interface UserDao {  
    public void methon();  
}
```

创建一个dao层接口的实现类：
```java
package org.example.dao.impl;

import org.example.dao.UserDao;
import org.springframework.stereotype.Component;

@Component("userDao")
public class UserDaoImpl implements UserDao {
	public void methon() {
		System.out.println("this is a methon");
	}
}
```

> [!NOTE] 
> 这里的dao层应该用的是`@Repository`注解，但是为了方便这里使用了`@Component`注解。两者的使用方式是一样的，只是可读性不同。
> 下面的service层也是。

在dao层上创建一个service层接口：
```java
package org.example.service;

public interface UserService {
	public void methon();
}
```

为service层接口创建一个实现类，注入dao层Bean对象。
```java
package org.example.service.impl;  
  
import org.example.dao.UserDao;  
import org.example.service.UserService;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.beans.factory.annotation.Qualifier;  
import org.springframework.stereotype.Component;  
  
@Component("userService")  
public class UserServiceImpl implements UserService {  
  
    @Autowired  
    @Qualifier("userDao") // 填写要注入的 Bean 的 id    
    private UserDao userDao;  
    public void setUserDao(UserDao userDao) {  
       this.userDao = userDao;  
    }  
  
    public void methon() {  
       userDao.methon();  
    }  
  
}
```

配置[[组件扫描]]。
```xml
<context:component-scan base-package="org.example"></context:component-scan>
```

在需要使用Bean时：
```java
package org.example.demo;  
  
import org.example.dao.UserDao;  
import org.example.service.UserService;  
import org.springframework.context.ApplicationContext;  
import org.springframework.context.support.ClassPathXmlApplicationContext;  
  
public class UserDaoDemo {  
    public static void main(String[] args) {  
       ApplicationContext app = new ClassPathXmlApplicationContext("applicationContext.xml");  
       UserService userService = (UserService) app.getBean("userService");  
       userService.methon();  
    }  
}
```
# 相关
返回：[[Spring 原始注解]]