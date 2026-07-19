---
updated: 2026-07-15 10:36
created: 2026-07-15 10:27
tags:
---
# 介绍
给表单元素使用，使数据能够双向绑定。
原来：数据变化 -> 视图变化。
现在：数据变化 <-> 视图变化。
# 使用方式
编写表单标签，加上`v-model`属性。
```HTML
<div id="app">
	<input type="text" v-model="username"><br>
	<input type="password" v-model="password"><br>
</div>
```

这样在输入框中的内容发生变化时，`v-model`绑定的变量内容也发生变化。
# 相关