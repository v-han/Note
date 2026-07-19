---
updated: 2026-07-14 20:20
created: 2026-07-14 18:18
tags:
---
# 介绍
可以使用标签来动态渲染HTML页面。
# 使用方式
编写`<div>`标签，给改标签加上`v-html`属性。
```HTML
<div id="app">
	<!-- v-html 标签里写表达式 -->
	<div v-html="msg"></div>
</div>
```

编写Vue实例，给表达式赋值。
```
<script>
	const app = new Vue({
		el:"#app",
		data:{
			msg:`
				<a href="https://www.bilibili.com">
					this is a web.
				</a>
				`
		}
	})
</script>
```

这样就将`msg`中的HTML内容渲染出来了。
# 相关