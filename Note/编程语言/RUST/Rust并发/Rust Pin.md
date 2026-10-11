---
created: 2026-10-11 16:52
updated: 2026-10-11 17:30
tags:
---
# 介绍
**Rust**的**Pin**是一个包装类型，用于限制值在内存中的移动。
# 使用方式
使用`Pin::new()`对一个数据在内存上进行固定。
```rust
// 固定 s 内存位置
let pinned = Pin::new(&a);
```

对于指针类型，固定的是指针指向的数据。
```rust
// Pin<Box<T>>
// 这里例子举得不好，String 是实现 Unpin 的，仍可以移动
let x = Box::pin(String::from("123"));
```

> [!NOTE]
> **Pin**通常用于异步的**Future**。**Future**在不同状态间保存局部变量，这些变量直接有着**自引用**的关系，随意移动会导致**引用**的丢失。

# 相关
[[Rust Unpin Trait]]