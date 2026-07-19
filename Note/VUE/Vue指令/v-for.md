---
updated: 2026-07-15 10:30
created: 2026-07-15 09:13
tags:
---
# 介绍
基于数据循环，多次渲染整个元素。可以基于数组，对象，数字。
# 使用方式
指定循环次数。
```HTML
<div id="app">
	<p v-for="i in 3">this is v-for</p>
</div>
```

要循环数组内容时。
```HTML
<div id="app">
	<ul>
		<li v-for="(item, index) in list">{{ item }}</li>
	</ul>
</div>
```

`item`：数组内的元素。
`index`：数组的下标，不需要时可以省略。
在使用`v-for`时最好加上`:key`[[v-for的key|属性]]来为元素添加**唯一标识**，便于Vue进行列表项的正确排序复用。
```HTML
<div id="app">
	<ul>
		<li v-for="(item, index) in list" :key="index">{{ item }}</li>
	</ul>
</div>
```
# 相关