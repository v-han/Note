---
updated: 2026-05-25 23:51
created: 2026-04-18 23:19
tags:
---
# 介绍
用于配置对象交由Spring来创建。
默认情况下调用类中的**无参构造函数**，如果没有则不能创建。
# Bean基本属性
1. id：Bean实例在Spring容器中的唯一标识，不可重复。
2. class：Bean的全限定名称。
3. scope：对象的作用范围。

| 取值范围           | 说明                                             |
| -------------- | ---------------------------------------------- |
| **singleton**  | 单例的，创建的对象实际上是一个(默认值)。                          |
| **prototype**  | 多例的，创建的对象是多个。                                  |
| request        | Web项目中，Spring创建一个对象，并将对象存入request域中。           |
| session        | Web项目中，Spring创建一个对象，并将对象存入session域中。           |
| global session | Web项目中，应用在Portlet环境，如果没有Portlet环境那么相当于session。 |
|                |                                                |
> [!note]
> scope为singleton时，在加载Spring配置文件时就创建对象。且只要容器在，对象就一直存活。
> scope为prototype时，在`getBean()`时创建对象，只有在对象使用时才存活，长时间不使用会被Java垃圾回收器回收。

4. init-methon：Bean对象的初始化方法，在对象创建之后。
5. destory-methon：Bean对象的销毁方法。
# Bean实例化
1. 无参构造方法实例化。
详细看[[Spring 快速入门|快速入门]]。
2. [[工厂静态方法实例化]]。
3. [[工厂实例方法实例化]]。
# 相关