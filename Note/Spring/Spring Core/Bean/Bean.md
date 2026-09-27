---
updated: 2026-09-21 23:08
created: 2026-09-19 22:42
tags:
---
# 介绍
**Bean**是**Spring IoC容器**创建和管理的**Java**对象。
# 使用方式
**Bean**有以下的属性：
1. **id**：**Bean**实例在**Spring容器**中的唯一标识，不可重复。
2. **class**：**Bean**的全限定类名。
3. **scope**：**Bean**的[[Bean Scope|作用范围]]。
4. **init-methon**：**Bean**的初始化方法，在**Bean**创建之后执行。
5. **destory-methon**：**Bean**的销毁方法，在**Bean**销毁后执行。

使用[[Bean XML配置|XML]]或[[Bean注解配置|注解]]的方式配置**Bean**，以及**Bean**的[[Bean依赖注入|依赖注入]]。
# 相关