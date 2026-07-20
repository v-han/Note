---
updated: 2026-07-20 22:51
created: 2026-07-14 23:25
tags:
---
# 介绍
用于动态设置HTML的标签属性，如src，url等。
# 使用方法
使用`v-bind:属性名="表达式"`方式为标签更改属性。
编写一个`<img>`标签加上`v-bind`标签。
```HTML
<div id="app">
	<img v-bind:src="imgUrl">
</div>
```

这样在Vue实例中就可以使用`imgUrl`变量动态调整图片。

为了简化，`v-bind:属性名`可以写成`:属性名`。
```HTML
<div id="app">
	<img :src="imgUrl">
</div>
```
# 相关