---
updated: 2026-06-11 20:46
created: 2026-06-08 00:25
tags:
---
# 介绍
在Web项目中，可以使用`ServletContextListener`监听Web应用。在Web应用启动时，加载Spring配置文件，创建应用上下文对象`ApplicationContext`并将其存储到最大的域`servletContext`域中，这样就可以在任意位置获得域中上下文对象`ApplicationContext`，避免了其的重复创建。
# 开发步骤
[[Spring 监听器]]
编写一个监听器：
```java
package org.example.listener;  
  
import org.example.config.SpringConfiguration;  
import org.springframework.context.ApplicationContext;  
import org.springframework.context.annotation.AnnotationConfigApplicationContext;  
  
import javax.servlet.ServletContext;  
import javax.servlet.ServletContextEvent;  
import javax.servlet.ServletContextListener;  
  
public class ContextLoaderListener implements ServletContextListener {  
  
    @Override // 初始化方法
	public void contextInitialized(ServletContextEvent servletContextEvent) {  
        ApplicationContext app = new AnnotationConfigApplicationContext(SpringConfiguration.class);  
  
        // 将 Spring 上下文对象存到 ServletContext 域中  
        ServletContext servletContext = servletContextEvent.getServletContext();  
        servletContext.setAttribute("app", app);  
    }  
  
    @Override // 销毁方法
    public void contextDestroyed(ServletContextEvent servletContextEvent) {  
  
    }  
}
```

在`web.xml`中配置监听器：
```xml
<listener>  
    <listener-class>org.example.listener.ContextLoaderListener</listener-class>  
</listener>
```

更改原来的Servlet类：
```java
package org.example.web;  
  
import org.example.service.UserService;  
import org.springframework.context.ApplicationContext;  
  
import javax.servlet.ServletContext;  
import javax.servlet.ServletException;  
import javax.servlet.http.HttpServlet;  
import javax.servlet.http.HttpServletRequest;  
import javax.servlet.http.HttpServletResponse;  
import java.io.IOException;  
  
public class UserServlet extends HttpServlet {  
  
    @Override  
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
        ServletContext servletContext = this.getServletContext();  
        ApplicationContext app = (ApplicationContext) servletContext.getAttribute("app");  
  
        UserService userService = (UserService) app.getBean("userService");  
        userService.methon();  
    }  
}
```


> [!NOTE] 
> 可以使用在 `web.xml`中使用`<context-param>`标签`<param-name>`，`<param-value>`存全局初始化参数。在用`ServletContext`的`getInitParameter()`方法得到初始化变量。

# 相关