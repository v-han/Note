---
updated: 2026-07-19 16:13
created: 2026-07-16 15:10
tags:
---
# 介绍
基于[[XMLHttpRequest]]对象封装，使用简单。
# 使用方式
引入对应的包
```HTML
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
```

使用[[axios函数]]。
```JavaScript
axios({
	url:"http://127.0.0.0:80/user"
}).then((result) => {
	// 拿到数据后的操作。
	console.log(result)
})
```
# 相关
[[async函数|axios异步]]实现方式。