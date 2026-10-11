---
updated: 2026-10-11 16:32
created: 2026-10-11 16:22
tags:
---
# 介绍
**Rust**的**Stream**是异步编程中的异步数据流**Trait**，可以理解为异步版本的迭代器。
# 使用方式
**Stream**不属于**Rust**标准库，通常需要**fetures**等第三方库提供。

使用`stream::iter`创建一个Stream。
```rust
// 将实现了 IntoIterator 的集合转换为 Stream
let mut stream = stream::iter(vec![1, 2, 3]);
```

使用**StreamExt Trait**为**Stream**提供的方法能够像**迭代器**一样使用异步**Stream**。
```rust
let x = stream.next().await;
```
# 相关