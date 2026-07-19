---
updated: 2026-07-16 14:00
created: 2026-07-13 22:53
tags:
---
# 介绍
这部分好像还是使用Vue2。可以去[官网](https://v2.cn.vuejs.org)看文档
# 开发步骤
准备容器。
```html
<div id="app">
	{{ msg }}
</div>
```

[[Vue插值表达式|双括号里的]]表示需要动态渲染的部分，可以在标签里加上[[Vue指令]]。
导入相关包。
```HTML
<!-- 这是开发版本的包 -->
<script src="https://cdn.jsdelivr.net/npm/vue@2.7.16/dist/vue.js"></script>

<!-- 这是生产版本的包 -->
<script src="https://cdn.jsdelivr.net/npm/vue@2.7.16"></script>

```

创建Vue实例。
```javascript
<script>
	const app = new Vue({
		el:'#app',
		data:{
			msg:'helloworld'
		},
		methods:{
		}
	})
</script>
```

`el`：用于指定挂载点，指定id的容器。
`data`：提供数据。
还可以加上[[Vue方法|methods(方法)]]，[[Vue计算属性|computed(计算属性)]]，[[Vue监视器|watch(监视器)]]。

# 相关