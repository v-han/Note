---
updated: 2026-09-27 01:24
created: 2026-09-26 18:27
tags:
---
# 介绍
**Rust**的**元组结构体**。
# 使用方式
使用`struct`关键字定义**结构体**以及其名称，在`()`内填写其字段的**数据类型**。
```rust
struct Point(i32, i32, i32);
```

使用点标记的方式访问其字段。
```rust
let point = Point(1, 2, 3);
println!("{}", point.0);
```
# 相关
和[[Rust Struct|结构体]]相比，其字段没有名字。
和[[Rust Tuple|元组]]相比，其是一个新的独立的类型。