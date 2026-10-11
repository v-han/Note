---
updated: 2026-10-11 16:52
created: 2026-10-10 01:58
tags:
---
# 介绍
**Rust**中的**Future**是**异步**编程的核心**Trait**，用于表示一个可能**尚未完成**、**未来会产生结果**的计算任务。
# 使用方式
使用`async`关键字定义一个**异步函数**或**代码块**。
```rust
async fn async_fun() -> Option<String> {
	// 具体实现
}

// 可以近似理解为以下形式
// 调用异步函数时，会返回一个实现了 Future 的类型
// Option<String> 是 Future 完成后返回的类型
fn async_fun() -> impl Future<Output = Option<String>> {
    async { // 具体实现 }
}
```

使用`await`等待一个**Future**的完成并获取其最终结果，若尚未完成会让出任务执行权，先执行别的代码。
```rust
// 只有带 await 的才会让出任务执行权
let async_res = async_fun().await;
```

> [!NOTE]
> `await`只能用于异步上下文中，必须放到`async`定义的范围内。
> 
> **Future**是**Rust**标准库提供的**Trait**，可以直接使用`async`和`await`。但**Future**本身不会自动执行，需要通过[[Rust异步运行时|执行器]]驱动。
# 相关
[[Rust Pin]]
[[Rust Stream]]
