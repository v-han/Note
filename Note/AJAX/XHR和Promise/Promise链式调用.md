---
updated: 2026-07-19 15:57
created: 2026-07-19 15:42
tags:
---
# 介绍
使用Promise链式调用解决[[回调函数地狱]]问题。
由于`.then()`方法的返回值就是一个Promise对象，用此来串联下一环任务。
# 使用方法
在外层的Promise对象的成功回调方法编写返回值。
```JavaScript
// 外层 Promise 对象创建略。
const p2 = p.then(result => {
	// 内层 Promise 对象创建。
	return new Promise((resolve, reject) => {
		setTimeout(() => {
			// 能拿到外层回调函数的值。
			resolve(result)
		}, 2000)
	})
})
```
# 相关