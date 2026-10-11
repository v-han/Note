---
updated: 2026-10-09 01:00
created: 2026-10-09 00:35
tags:
---
# 介绍
**Rust**的**Rc智能指针**的**弱引用**，即不会增加**强引用**计数，因此不会阻止数据被清理。
# 使用方式
使用`Rc::downgrade`创建**Rc指针**的**Weak弱引用**。
```rust
let a = Rc::new(5);
// b 是 Weak<i32> 类型
let b = Rc::downgrade(&a);
```

访问其中的数据时需要使用`upgrade`方法查看**被引用的数据**是否存在。
```rust
// 返回的类型是 Option<T>
if let Some(value) = weak.upgrade() {}
```
# 相关