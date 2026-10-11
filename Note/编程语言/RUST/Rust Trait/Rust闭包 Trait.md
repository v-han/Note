---
updated: 2026-10-06 14:55
created: 2026-10-06 01:13
tags:
---
# 介绍
**Rust**会对对应的**闭包**自动实现对应的**Trait**。
# 使用方式
**Rust**的**闭包**有以下几种**Trait**。
**FnOnce**：所有闭包都实现的**Trait**。获得所有权，若消耗了**所有权**只能使用一次。
**FnMut**：实现**FnOnce**。捕获**可变引用**，可以使用多次。
**Fn**：实现**FnOnce**和**FnMut**。捕获**不可变引用**，可以使用多次。

可以在函数中对**闭包**使用**Trait约束**，这里以`unwrap_or_else`为例。
```rust
impl<T> Option<T> {
	pub fn unwrap_or_else<F>(self, f: F) -> T
	where
		// 若需要用到闭包的返回值需要指定类型
		F: FnOnce() -> T
	{
		match self {
			Some(x) => x,
			None => f(),
		}
	}
}
```
# 相关
[[Rust Trait]]