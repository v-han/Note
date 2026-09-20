---
updated: 2026-09-20 23:41
created: 2026-09-20 01:20
tags:
---
# 介绍
**Spring**的**应用上下文**(ApplicationContext)的**XML**配置方式。
# 使用方式
在**resources**目录下创建一个`applicationContext.xml`(名字没有要求，这里只是约定俗成)，有关`<beans>`的头部声明略过。有关配置**应该**写到`<beans>`标签中。

使用`bean`标签来配置对应的Bean。
```xml
<bean id="userDao" class="org.example.dao.impl.UserDaoImpl"></bean>
```

使用`import`标签导入其他的**应用上下文XML**配置文件。
```xml
<import resourse="applicationContext-user.xml/>
```

使用`context:property-placeholder`标签加载**porperty**配置文件，在使用的时候只用`"${配置文件中的key}"`便可取出该配置文件的值。
```xml
<!-- 加载类路径下的 db.property 配置文件 -->
<context:property-placeholder location="classpath:db.property"/>
```
# 相关