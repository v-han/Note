---
updated: 2026-08-06 13:26
created: 2026-08-04 14:36
tags:
---
# 介绍
**RUST**的控制流中的条件判断。
# 使用方式
和其他语言一样可以用`if`、`else if`和`else`进行条件控制。
```rust
if num > 5 {
	println!("num is bigger then 5");
} else if num < 2{
	println!("num is smaller then 2");
} else {
	println!("other");
}
```

> [!NOTE]
> 和C语言等不同，条件表达式的结果类型必须是`bool`类型的。
# 相关