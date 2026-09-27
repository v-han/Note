---
updated: 2026-09-22 22:16
created: 2026-09-20 01:20
tags:
---
# 介绍
使用**XML**方式配置**Spring**的**应用上下文**(ApplicationContext)。
# 使用方式
在**resources**目录下创建一个`applicationContext.xml`(名字没有要求，这里只是约定俗成)，有关`<beans>`的头部声明略过。有关配置**应该**写到`<beans>`标签中。

使用`bean`标签来配置对应的**Bean**。
```xml
<bean id="userDao" class="org.example.dao.impl.UserDaoImpl"></bean>
```

使用`import`标签导入其他的**应用上下文XML**配置文件。
```xml
<!-- 导入 applicationContext-user.xml -->
<import resourse="applicationContext-user.xml/>
```

使用`context:property-placeholder`标签加载**porperty**配置文件，在使用的时候只用`"${配置文件中的key}"`便可取出该配置文件的值。
```xml
<!-- 加载类路径下的 db.property 配置文件 -->
<context:property-placeholder location="classpath:db.property"/>
```

使用`context:component-scan`标签配置**组件扫描**的包。
```xml
<!-- 扫描 org.example 包下的组件 -->
<context:component-scan base-package="org.example"></context:component-scan>
```
# 相关