---
updated: 2026-09-20 18:59
created: 2026-04-21 00:01
tags:
---
# 介绍
**Bean**的**工厂实例方法**配置方法。
# 使用方式
创建一个**动态工厂类**，添加实例化**Bean**的方法：
```java
public class DynamicFactory {
	public UserDao getUserDao() {
		return new UserDaoImpl();
	}
}
```

在[[Spring应用上下文XML配置|配置文件]]中添加：
```xml
<!-- 先配置工厂的 Bean -->
<bean id="factory" class="org.example.factory.DynamicFactory"></bean>

<!-- 再配置所需对象的 Bean -->
<bean id="userDao" factory-bean="factory" factory-method="getUserDao">
```
# 相关