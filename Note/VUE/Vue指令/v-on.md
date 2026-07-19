---
updated: 2026-07-14 23:20
created: 2026-07-14 20:49
tags:
---
# 介绍
用于监听与提供事件对应的处理逻辑。
# 使用方式
编写一个`<button>`标签，加上`v-on`属性。
```HTML
<div id="app">
	<!-- v-on:事件="处理逻辑" -->
	<!-- 处理逻辑可以是函数也可以是内联语句 -->
	<button v-on:click="count++">this is a button</button>
</div>
```

这样点击这个按钮之后`count`的值就会加一。

> [!NOTE]
> 使用内联语句能够直接拿到Vue实例中的数据，而使用[[Vue方法|方法]]方式需要用`this`获取。

为了简化，`v-on:事件`也可以写成`@事件`。
```HTML
<div id="app">
	<button @click="count++">this is a button</button>
</div>
```
# 相关