---
updated: 2026-09-30 00:35
created: 2026-09-30 00:12
tags:
---
# 介绍
**Rust**的**解引用**，能够操作引用变量的数据。
# 使用方式
使用`*`对引用变量进行解引用。
```rust
let x = 3;
let y = &x;
// 此时 x 的值为 4
*y += 1;
```

也可以对指向堆内存上的指针进行**解引用**。
```rust
let x = Box::new(3);
*x += 1;
```

Rust也存在一些隐式**解引用**。
```rust
let x = Box::new(-1);
let x_abs1 = i32::abs(*x);  // 显式解引用
let x_abs2 = x.abs();       // 隐式解引用

// rust 也支持多层隐式解引用
let y = &x;
let y_abs1 = i32::abs(**y); // 显式解引用
let y_abs2 = y.abs();       // 隐式解引用
```
# 相关