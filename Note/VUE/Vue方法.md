---
updated: 2026-07-14 23:18
created: 2026-07-14 23:09
tags:
---
# 介绍
在Vue中使用方法。
# 使用方式
在Vue实例中的methods部分编写Vue方法。
```JavaScript
const app = new Vue({
		el:'#app',
		data:{
		},
		methods:{
			function () {
				return "this is a method"
			}
		}
	})
```

> [!NOTE]
> 要使用Vue实例中的数据部分，需要在前面加上`this`。

# 相关