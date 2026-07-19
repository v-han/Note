---
updated: 2026-07-19 14:04
created: 2026-07-19 13:51
tags:
---
# 介绍
由于等待服务器回应是耗时操作，结合[[Promise]]和[[XMLHttpRequest]]异步完成发送请求操作。
# 使用方式
创建Promise对象，在其中编写XMLHttpRequest对象对服务器发出访问。
```JavaScript
const p = new Promise((resolve, reject) => {
	const xhr = new XMLHttpRequest()
	xhr.open('GET', 'http://127.0.0.0:80/user')
	xhr.addEventListener('loadend', () => {
		// 查看返回状态码。
		if (xhr.status >= 200 & xhr.status < 300) {
			resolve(JSON.parse(xhr.response))
		} else {
			reject(new Error(xhr.response))
		}
		xhr.send()
	})
})

// 关联成功失败回调函数。
p.then(result => {
	console.log(result)
}).catch(error => {
	console.log(error)
})
```
# 相关