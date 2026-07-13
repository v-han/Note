---
updated: 2026-06-08 23:09
created: 2026-06-01 21:59
tags:
  - "#question"
---
# 介绍
Spring与[[JavaWeb Guide|JavaWeb]]继承。
# 开发步骤
导入servlet坐标。
```Maven
<!-- servlet -->
<dependency>  
    <groupId>javax.servlet</groupId>  
    <artifactId>javax.servlet-api</artifactId>  
    <version>3.1.0</version>  
    <scope>provided</scope>  
</dependency>  

<!-- servlet.jsp -->
<dependency>  
    <groupId>javax.servlet.jsp</groupId>  
    <artifactId>javax.servlet.jsp-api</artifactId>  
    <version>2.2.1</version>  
    <scope>provided</scope>  
</dependency>
```

编写一个Servlet类：
```java
package org.example.web;  
  
import org.example.config.SpringConfiguration;  
import org.example.service.UserService;  
import org.springframework.context.ApplicationContext;  
import org.springframework.context.annotation.AnnotationConfigApplicationContext;  
  
import javax.servlet.ServletException;  
import javax.servlet.http.HttpServlet;  
import javax.servlet.http.HttpServletRequest;  
import javax.servlet.http.HttpServletResponse;  
import java.io.IOException;  
  
public class UserServlet extends HttpServlet {  
  
    @Override  
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
        ApplicationContext app = new AnnotationConfigApplicationContext(SpringConfiguration.class);  
        UserService userService = (UserService) app.getBean("userService");  
        userService.methon();  
    }  
}
```

配置servlet映射(web.xml)：
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"  
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"  
         version="4.0">  
  
    <servlet>  
       <servlet-name>UserServlet</servlet-name>  
       <servlet-class>org.example.web.UserServlet</servlet-class>  
    </servlet>  
      
    <servlet-mapping>  
       <servlet-name>UserServlet </servlet-name>  
       <url-pattern>/userServlet</url-pattern>  
    </servlet-mapping>  
  
</web-app>
```

[[ContextLoaderListener配置]]
# 相关