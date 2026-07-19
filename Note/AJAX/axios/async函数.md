---
updated: 2026-07-19 16:38
created: 2026-07-19 16:11
tags:
---
# 介绍
async函数使使用`async`关键字声明的函数。async函数使AsyncFunction构造函数的实例，并在其中运行使用`await`关键字。
# 使用方式
使用`async`关键字修饰方法，在方法内使用`await`关键字修饰异步代码部分。
```JavaScript
async function getData() {
	const cObj = await axios({url:'http://127.0.0.0:80/class'})
	const name = obj.data.name
	const uObj = await axios({url:'http://127.0.0.0:80/user', params:{ name }})
}
```

在遇到`await`关键字后的代码会先执行下面代码，可以实现多个axios的串行调用。同时便于代码的编写和增强可读性。
# 相关
[[async错误处理]]