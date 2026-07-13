---
updated: 2026-07-07 00:45
created: 2026-06-08 20:49
tags:
---
# 介绍
# 开发步骤
编写一个Servlet类继承HttpServlet，并覆写`doGet`(Get请求，其他同理)方法:
```java
package org.example.servlet;

import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;  
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

public class FirstServlet extends HttpServlet {
	protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
		System.out.println("this is a servlet");
	}
}
```

在`web\WEB-INF\web.xml`(创建web项目会自动创建，或者在项目结构中添加)编写：
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"  
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_3_0.xsd"  
         version="4.0">  
  
	<servlet>
		<!-- 名字 -->
		<servlet-name>FirstServlet</servlet-name>
		<!-- 对应的类 -->
		<servlet-class>org.exampl.servlet.FirstServlet</servlet-class>  
    </servlet>  
      
    <servlet-mapping> 
	    <!-- 与上边servlet标签名字一致 -->
		<servlet-name>FirstServlet</servlet-name>
		<!-- 对应的路径 -->  
		<url-pattern>/firstServlet</url-pattern>  
    </servlet-mapping>  
  
</web-app>
```

在项目结构中配置对应的[[Tomcat]]然后运行。
# 相关