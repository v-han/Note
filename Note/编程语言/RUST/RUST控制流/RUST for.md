---
updated: 2026-09-27 18:26
created: 2026-08-04 16:49
tags:
---
# 介绍
**Rust**的循环控制流，使用`for`进行循环遍历集合。
# 使用方式
使用`for`循环来遍历集合，相较[[Rust while|while]]和[[Rust loop|loop]]更加安全和高效。
```rust
let a = [1, 2, 3, 4];
for i in a {
	println!("{}", i);
}
```

配合[[Rust Range|range]]进行自定义的循环遍历。
# 相关