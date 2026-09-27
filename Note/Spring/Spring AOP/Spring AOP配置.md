---
updated: 2026-09-24 15:57
created: 2026-09-24 15:38
tags:
---
# 介绍
**SpringAOP**的配置。
# 使用方式
定义一个通知类管理切面，并将该类交由[[Spring Core|Spring IoC容器]]管理。
```java
@Component
// 表示当前 Bean 是切面管理类
@Aspect
public class MyAdvice {}
```

在类中定义[[Spring AOP切入点|切入点]]。
```java
@Pointcut("execution(* org.example.dao.**)")
private void pc(){}
```

在类中定义[[Spring AOP通知|通知方法]]。
```java
@Before("pt()")
public void method() {
	// 通知方法
}
```

在[[Spring应用上下文注解配置|Spring应用上下文]]配置类上添加`@EnableAspectJAutoProxy`，表示启用了注解开发的**AOP**。
```java
@Configuration
@ComponentScan("org.example")
@EnableAspectJAutoProxy
public class SpringConfig {}
```
# 相关