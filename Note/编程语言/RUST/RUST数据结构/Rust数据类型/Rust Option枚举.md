---
updated: 2026-09-27 18:09
created: 2026-09-27 17:46
tags:
---
# 介绍
**Rust**没有`Null`的类型，使用**Option**的方式使程序员考虑值可能不存在的情况。
# 使用方式
`Option`是**Rust**的一个枚举类，其定义如下。
```rust
enum Option<T> {
	Some(T),
	None,
}
```

因为`Option`在预导入模块，可以直接使用。
```rust
let some_number = Some(6);
let some_string = Some("A String");

// 使用 None 时无法推导其类型，需要指定
let none_number: Option<i32> = None;
```
# 相关