---
updated: 2026-07-19 13:12
created: 2026-07-19 12:40
tags:
---
# 介绍
Promise对象有三种状态：待定(pending)，已兑现(fulfilled)和已拒绝(rejected)。
# 内容
在Promise对象创建时为**待定**状态。
当执行了resolve()方法之后就变为**已兑现**，会执行`.then()`方法。
当执行了reject()方法之后就变为**已拒绝**，会执行`.catch()`方法。

> [!NOTE]
> 一但Promise对象被兑现或拒绝状态就无法改变，即调用完`resolve()`或`reject()`方法之后再执行另一个函数也不会改变状态。
# 相关