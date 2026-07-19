---
updated: 2026-07-18 15:02
created: 2026-07-18 14:48
tags:
---
# 介绍
使用XMLHttpRequest对象的请求体传参。
# 使用方式
在创建完XMLHttpRequest对象后，为该对象发送的Http报文添加首部。
```JavaScript
xhr.setRequestHeader('Content-Type', 'application/json')
```

定义要发送的JSON格式的JS对象，并将其转换为字符串型。
```JavaScript
const user = { username:"Tom", age:20 }
const userStr = JSON.stringify(user)
```

发送时带上这个字符串参数。
```JavaScript
xhr.send(userStr)
```
# 相关