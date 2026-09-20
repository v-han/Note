---
updated: 2026-09-19 23:08
created: 2026-09-19 23:04
tags:
---
# 介绍
**Bean**的**作用范围**。
# 作用范围
| 取值范围           | 说明                                             |
| -------------- | ---------------------------------------------- |
| **singleton**  | **单例的**，创建的对象实际上是一个(默认值)。                      |
| **prototype**  | **多例的**，创建的对象是多个。                              |
| request        | Web项目中，Spring创建一个对象，并将对象存入request域中。           |
| session        | Web项目中，Spring创建一个对象，并将对象存入session域中。           |
| global session | Web项目中，应用在Portlet环境，如果没有Portlet环境那么相当于session。 |
> [!note]
> **scope**为**singleton**时，在加载**Spring**配置文件时就创建对象。且只要容器在，对象就一直存活。
> **scope**为**prototype**时，在`getBean()`时创建对象，只有在对象使用时才存活，长时间不使用会被Java垃圾回收器回收。
# 相关