---
updated: 2026-10-02 20:40
created: 2026-10-02 16:35
tags:
---
# 介绍
**Rust**的**错误处理**。**Rust**将错误分为**可修复**的和**不可修复**的。
# 使用方式
**Rust**中使用[[Rust Panic|panic]]表示**不可恢复**的错误。
```rust
panic!("Error occur")
```

**Rust**中使用[[Rust Result|Result]]处理**可恢复**的错误。配合[[Rust传播错误|错误传播]]可以捕获错误并进行处理。
# 相关