---
updated: 2026-09-21 21:09
created: 2026-04-19 23:45
tags:
---
# 介绍
**P命名空间**注入本质也是**set方法依赖注入**，但是比**set方法依赖注入**更加方便。
# 使用方式
在**配置文件**中的`<beans>`(有**s**)标签中添加：
```xml
xmlns:p="http://www.springframework.org/schema/p"
```

然后也要修改注入方式：
```xml
<bean id="userService" class="org.example.service.impl.UserServiceImpl" p:userDao-ref="userDao"/>
```
# 相关