---
updated: 2026-07-16 20:00
created: 2026-07-16 15:32
tags:
---
# 介绍
# 使用方式
直接拼接的方式。
```JavaScript
axios({
	url:"http://127.0.0.0:80/user",
	params:{
		id:1
	}
}).then((result) => {
	// 拿到数据后的操作。
	console.log(result)
})
```

`param`：直接拼接到url后面的参数。

使用其他请求方式。
```JavaScript
axios({
	url:"http://127.0.0.0:80/user",
	method:"GET",
	data:{
		id:1
	}
}).then((result) => {
	// 拿到数据后的操作。
	console.log(result)
})
```

`method`：请求方式，默认为GET，不区分大小写。
`data`：提交的数据。
# 相关
若服务器发送错误回来，可以加上[[axios错误处理]]。