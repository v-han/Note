---
updated: 2026-07-19 16:38
created: 2026-07-16 20:01
tags:
---
# 介绍
在[[axios函数]]之后捕获服务器返回错误，进行处理。
# 使用方式
在原[[axios函数]]调用之后加上`.catch()`函数，在内部编写对应的错误处理逻辑。
```JavaScript
axios({
	url:"http://127.0.0.0:80/user",
}).then((result) => {
	// 拿到数据后的操作。
	console.log(result)
}).catch(error => {
	// 处理错误信息。
	console.log(error)
})
```
# 相关