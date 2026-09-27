---
updated: 2026-09-25 02:48
created: 2026-09-25 01:33
tags:
---
# 介绍
**Rust**的可变引用。
# 使用方式
在类型前加上`mut`表示该引用数据类型时可变的。
```rust
// 原本的变量也必须是可变的
let mut s1 = String::from("hello");
// &mut String 表示是可变的引用类型
// &mut s1 表示取到 s1 的可变引用变量
let s2: &mut String = &mut s1;
```

> [!NOTE]
> 在一个作用域中，一个可变变量**只能**存在一个可变的引用变量，且有了可变引用也无法创建**普通引用**。
> ```rust
> let mut s = String::from("hello");
> let s1 = &mut s;
> // 不允许再对 s 取引用，以下语句都是不被允许的
> // let s2 = &mut s;
> // let s3 = &s;
> ```
# 相关