---
updated: 2026-09-21 21:08
created: 2026-04-20 00:13
tags:
---
# 介绍
使用**set方法**为**Bean**注入所需的依赖。
# 使用方式
在**配置文件**中在`bean`标签中配置**Bean**所需的依赖。`name`属性表示要注入的元素，`value`和`ref`表示注入的**值**和**Bean**。
```xml
<bean id="userService" class="org.example.service.impl.UserServiceImpl">
	<!-- 配置注入的普通数据类型 -->
	<property name="username" value="Tom"></property>

	<!-- 配置注入的引用数据类型，即注入其他的 Bean -->
	<property name="userDao" ref="userDao"></property>
	
	<!-- 配置注入的集合数据类型 -->
	<property name="strList">
		<list>
			<!-- 如果注入集合的元素是 Bean，这里用 ref 标签 -->
			<value>String1</value>
			<value>String2</value>
		</list>
	</property>
</bean>
```

> [!NOTE]
> 使用**set方法**注入时，需要确保需要注入的元素有对应的**set方法**。
> 且满足一定的命名规范(set方法和`name`属性都符合**驼峰命名**)，例如`setUsername`->`username`。
# 相关
[[P命名空间注入]]