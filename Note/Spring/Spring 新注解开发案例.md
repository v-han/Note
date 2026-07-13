---
updated: 2026-06-08 00:17
created: 2026-05-27 15:48
tags:
---
# 开发步骤
编写一个配置类：
```java
package org.example.config;  
  
import org.springframework.context.annotation.ComponentScan;  
import org.springframework.context.annotation.Configuration;  
import org.springframework.context.annotation.PropertySource;  
  
@Configuration  
@ComponentScan("org.example") // 组件扫描  
@PropertySource("classpath:db.properties") // 加载配置文件
@Import({anotherconfig.class}) // 加载另一个配置文件
public class SpringConfiguration {  
  
}
```

[[数据源注解配置]]

编写一个demo测试：
```java
package org.example.demo;  
  
import org.example.config.SpringConfiguration;  
import org.example.service.UserService;  
import org.springframework.context.ApplicationContext;  
import org.springframework.context.annotation.AnnotationConfigApplicationContext;  
  
public class demo {  
    public static void main(String[] args) {  
        ApplicationContext app = new AnnotationConfigApplicationContext(SpringConfiguration.class);  
        UserService userService = app.getBean(UserService.class);  
        userService.methon();  
    }  
}

```

> [!tip]
> 这里要注意下`jdk`版本和`Spring context`。

# 相关