---
updated: 2026-09-27 18:24
created: 2026-08-04 15:48
tags:
---
# 介绍
**Rust**的循环控制流，使用`loop`进行循环。
# 使用方式
使用`loop`关键字来定义要循环的部分。
```rust
loop {
	println!("hello");
}
```

> [!NOTE]
> `loop`会一直循环下去，除非主动叫停程序。一般都需要配合`break`关键字。
# 相关