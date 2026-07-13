---
updated: 2026-04-20 00:26
created: 2026-04-19 23:45
tags:
---
# 介绍
P命名空间注入本质也是[[set方法依赖注入]]，但是比set方法依赖注入更加方便。
# 注入方式
在applicationContext.xml文件中的`<beans>`(有**s**)标签中添加：
```xml
xmlns:p="http://www.springframework.org/schema/p"
```

然后也要修改注入方式：
```xml
<bean id="userService" class="org.example.service.impl.UserServiceImpl" p:userDao-ref="userDao"/>
```
# 相关