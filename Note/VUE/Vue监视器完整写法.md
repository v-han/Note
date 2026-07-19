---
updated: 2026-07-16 10:55
created: 2026-07-16 10:38
tags:
---
# 介绍
在[[Vue监视器]]添加额外的配置项。
# 使用方式
可以添加`deep:true`属性进行深度监视，当对象属性发生变化时也进行操作。
```JavaScript
watch:{
	obj:{
		deep:true,
		// 业务逻辑代码
		handler (newValue) {
			console.log(newValue)
		}
	}
}
```

如果希望不仅仅在数据修改时执行业务逻辑，还想要在页面初始化时执行，可以加上`immediate:true`属性。
```JavaScript
watch:{
	obj:{
		deep:true,
		immediate:true,
		handler (newValue) {
			console.log(newValue)
		}
	}
}
```
# 相关