---
updated: 2026-10-11 16:15
created: 2026-10-10 16:56
tags:
---
# 介绍
**Rust**中的**异步运行时**(Async Runtime)负责驱动和调度**Future** 的执行，让**异步任务**能够运行起来。
通常**Rust**程序入口`main`函数不是异步的，如果需要在程序入口中执行异步代码，可以通过以下方式使用**异步运行时**。
# 使用方式
使用**Tokio**库的`tokio::main`宏执行异步的`main`函数。
```rust
#[tokio::main]
async fn main() {
    let async_res = async_fun().await;
}
```

使用**futures**库的`block_on`驱动**异步运行时**。
```rust
fn main() {
    let async_res = futures::executor::block_on(async_fun());
}
```
# 相关