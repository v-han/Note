---
updated: 2026-09-20 18:59
created: 2026-04-20 23:59
tags:
---
# 介绍
**Bean**的**工厂静态方法**配置方法。
# 使用方式
创建一个**对象工厂类**，添加实例化**Bean**的静态方法：
```java
public class StaticFactory {
	public static UserDao getUserDao() {
		return new UserDaoImpl
	}
}
```

在[[Spring应用上下文XML配置|配置文件]]中添加：
```xml
<bean id="userDao" class="org.example.factory.StaticFactory" factory-method="getUserDao"></bean>
```
# 相关