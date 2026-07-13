---
updated: 2026-04-25 01:06
created: 2026-04-20 00:13
tags:
---
# 介绍
依赖注入的一种方法。
# 注入方式
`UserDao`相关的代码略。
创建业务层接口代码：
```java
package org.example.service;

public interface UserService {
	public void methon();
}
```

创建业务层实现代码：
```java
package org.example.service.impl;  
  
import org.example.dao.UserDao;  
import org.example.service.UserService;  
  
public class UserServiceImpl implements UserService {  
      
    private UserDao userDao;  
      
    public void setUserDao(UserDao userDao) {  
       this.userDao = userDao;  
    }  
      
    public void methon() {  
       userDao.methon();  
    }  
  
}
```

在applicationContext.xml文件中添加对应的Bean：
```xml
<bean id="userService" class="org.example.service.impl.UserServiceImpl">
	<property name="userDao" ref="userDao"></property>
</bean>
```

> [!note]
> `<property>`标签中的`name`元素不是userDao这个Bean名字。而是`setUserDao()`方法在set之后的字母按照驼峰命名规范的变量名。这里只是一样而已。
> `ref`元素才是Bean的名字。

若添加的是普通数据类型时(假设类中已添加对应的属性，即`username`(类型为String)和`age`(类型为int)和对应的set方法)：
```java
	private String username;
	private int age;
	
	public void setUsername(String username) {
		this.username = username;
	}
	
	public void setAge(int age) {
		this.age = age;
	}
```

Bean标签的书写格式为：
```xml
<bean id="userService" class="org.example.service.impl.UserServiceImpl">
	<property name="username" value="名字"></property>
	<property name="age" value="20"></property>
</bean>
```

若添加的是集合数据类型时(假设类中已添加对应的属性，即`strList`和对应的set方法)
```java
	private List<String> strList;

	public void setStrList(List<String> strList) {
		this.strList = strList;
	}
```

Bean标签的书写格式为：
```xml
<bean id="userService" class="org.example.service.impl.UserServiceImpl>
	<property name="strList">
		<list>
			<value></value>
		</list>
	</property>
</bean>
```

> [!NOTE]
> 有多少个元素就在`<list>`标签中添加多少个`<value>`标签。
> 当注入的集合数据类型的元素是Bean时，可以使用`<ref>`标签。
> 其他集合数据类型只需要替换`<list>`标签为其对应的标签。

还有一种简单的方法：[[P命名空间注入]]
# 相关