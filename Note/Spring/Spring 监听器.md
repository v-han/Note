---
updated: 2026-09-19 01:45
created: 2026-06-11 20:46
tags:
---
# 介绍
# 开发步骤
导入spring-web坐标：
```Maven
<dependency>  
    <groupId>org.springframework</groupId>  
    <artifactId>spring-web</artifactId>  
    <version>7.0.5</version>  
</dependency>
```

配置web.xml：
```xml
<listener>  
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>  
</listener>  
  
<context-param>  
    <param-name>contextConfigLocation</param-name>  
    <param-value>classpath:applicationContext.xml</param-value>  
</context-param>
```
# 相关