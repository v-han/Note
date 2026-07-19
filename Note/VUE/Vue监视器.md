---
updated: 2026-07-16 10:38
created: 2026-07-15 20:51
tags:
---
# 介绍
监视数据变化，根据变化执行一些业务逻辑或异步操作。
# 使用方式
在Vue实例中的watch部分添加监视器，与要监视的属性名一致。
```JavaScript
const app = new Vue({
		el:'#app',
		data:{
			word:""
		},
		watch:{
			word (newValue, oldValue) {
				console.log("before", oldValue, "after", newValue)
			}
		}
	})
```

利用新值和旧值进行业务逻辑的操作。

> [!NOTE]
> 对象里的属性也要将对象和属性名都写出来，但是在JavaScript中方法名是不能带特殊字符的，要加上引号，例如`'obj.word'`。
# 相关
使用[[Vue监视器完整写法]]，可以添加配置项，实现更多操作。