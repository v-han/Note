---
updated: 2026-07-14 20:48
created: 2026-07-14 20:36
tags:
---
# 介绍
配合[[v-if]]来条件渲染。
# 使用方式
在有`v-if`属性的标签后面，编写`<div>`标签，添加`v-else`或`v-else-if`属性。
```HTML
<div id="app">
	<div v-if="score >= 90">it's good</div>
	<div v-else-if="score >= 60">it's ok</div>
	<div v-else>it's bad</div>
<div>
```

这样可以根据数据渲染不同的元素。

> [!NOTE]
> 需要紧挨着`v-if`属性的标签填写。
# 相关
需要[[v-if]]配合。