---
updated: 2026-10-12 20:01
created: 2026-10-12 19:36
tags:
---
# 介绍
**Rust**的**原始指针**(Raw Pointer)是一种直接指向内存地址的指针。
# 使用方式
Rust的**原始指针**有两种：**不可变指针**`*const T`和**可变指针**`*mut T`。
```rust
let mut num = 3;
// 不可变原始指针
let r1: *const i32 = &raw const num;
// 可变原始指针
let r2: *mut i32 = &raw mut num;
```

使用`as`进行类型转换获得**原始指针**。
```rust
let ptr: *const i32 = &num as *const i32;
```

> [!NOTE]
> **原始指针**可以忽略借用规则(一个可变引用或多个不可变引用)，且不保证指向地址的有效性，可用于较底层的操作。因此在使用**原始指针**是需要开发者自行保证安全性。
# 相关