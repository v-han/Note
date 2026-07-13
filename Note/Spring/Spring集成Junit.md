---
updated: 2026-06-01 22:27
created: 2026-06-01 21:41
tags:
---
# 介绍

# 开发步骤
导入Junit的坐标和Spring集成Junit包的坐标。
```Maven
<!-- Junit -->
<dependency>  
    <groupId>junit</groupId>  
    <artifactId>junit</artifactId>  
    <version>4.13.2</version>  
    <scope>test</scope>  
</dependency>

<!-- Spring集成Junit包 -->
<dependency>  
    <groupId>org.springframework</groupId>  
    <artifactId>spring-test</artifactId>  
    <version>6.2.14</version>  
</dependency>
```

编写测试类：
```java
package org.example;  
  
import org.example.config.SpringConfiguration;  
import org.example.service.UserService;  
import org.junit.Test;  
import org.junit.runner.RunWith;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.test.context.ContextConfiguration;  
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;  
  
@RunWith(SpringJUnit4ClassRunner.class)  
//@ContextConfiguration("classpath:applicationContext.xml") // 配置文件  
@ContextConfiguration(classes = {SpringConfiguration.class}) // 注解  
public class SpringJunit {  
  
    @Autowired  
    private UserService userService;  
  
    @Test  
    public void test1() {  
        userService.methon();  
    }  
  
}
```
# 相关
下一篇：[[Spring与Web环境集成]]