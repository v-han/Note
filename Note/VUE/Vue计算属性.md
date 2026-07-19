---
updated: 2026-07-15 20:51
created: 2026-07-15 18:32
tags:
---
# 介绍
基于现有的属性，计算出来的新属性。根据数据的变化自动计算。
# 使用方式
在Vue实例中的computed部分添加计算属性。
```JavaScript
const app = new Vue({
		el:'#app',
		data:{
			num1:1,
			num2:2
		},
		computed:{
			sum () {
				return this.num1 + this.num2
			}
		}
	})
```

编写的计算属性要写成方法形式。

> [!NOTE]
> 计算属性本质上还是属性，在使用[[Vue插值表达式|插值表达式]]的时候以属性形式，而不是以方法形式。

当需要修改计算属性也会修改原来的属性，可以使用计算属性的完整写法。
```JavaScript
computed:{
	sum:{
		// 被获取值的会触发get(),有缓存。
		get () {
			return this.num1 + this.num2
		},
		// 当计算属性被修改，会触发set()。
		set (value) {
			// 传入的形参就是计算属性
			this.num1 = value / 2
			this.num2 = value - this.num1
		}
	}
}
```

这样就可以用原来的属性来控制计算属性，也可以使用计算属性来控制原来的属性。
# 相关
对比：[[Vue方法]]更加侧重业务逻辑。**计算属性**是有缓存的，当数据更新立即计算出结果并缓存，性能更好。