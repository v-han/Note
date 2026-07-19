---
updated: 2026-07-19 15:57
created: 2026-07-19 12:24
tags:
---
# 介绍
Promise对象用于表示一个异步操作最终完成(或失败)及其结果。
# 使用方式
创建一个Promise对象。
```JavaScript
const p = new Promise((resolve, reject) => {
	// 执行异步代码，用等待方式模拟耗时代码。
	setTimeout(() => {
		// resolve 是成功调用。
		resolve('success')
		// reject 是失败调用。
		reject('error')
	}, 2000)
})
```

> [!NOTE]
> `resolve`和`reject`相关可以看[[Promise三种状态]]

获取结果。
```JavaScript
p.then(result => {
	console.log(result)
}).cathc(error => {
	console.log(error)
})
```
# 相关
多层异步调用要用[[Promise链式调用]]。