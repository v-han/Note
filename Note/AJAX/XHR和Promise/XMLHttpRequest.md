---
updated: 2026-07-19 13:51
created: 2026-07-17 13:42
tags:
---
# 介绍
使用XMLHttpRequest(XHR)对象用于与服务器交互。
# 使用方式
新建一个`XMLHttpRequest`对象。
```JavaScript
const xhr = new XMLHttpRequest()
```

为这个对象绑定请求方式和请求网址，可以使用拼接的方式携带请求参数或使用[[XHR请求体传参|请求体传参]]。
```JavaScript
xhr.open("GET", "http://127.0.0.0:80/user")
```

配置监听的事件和对应的处理代码。
```JavaScript
xhr.addEventLister("loadend", () => {
	console.log(xhr.response)
})
```

> [!NOTE]
> 这里使用`xhr.response`获取服务器返回结果。返回结果是字符串类型的，还需要`JSON.parse()`方法。

发送请求。
```JavaScript
xhr.send()
```
# 相关
使用[[Promise]]实现异步功能。
[[XHR结合Promise|结合Promise使用方式]]