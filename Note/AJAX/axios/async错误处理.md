---
updated: 2026-07-19 16:41
created: 2026-07-19 16:38
tags:
---
# 介绍
async函数使用`try`和`catch`来捕获错误。
# 使用方式
使用`try`和`catch`来捕获错误。
```JavaScript
async function getData() {
	try {
		// 要执行的 axios 代码，略。
	} catch(error) {
		console.log(error)
	}
}
```
# 相关