---
updated: 2026-08-06 14:07
created: 2026-08-04 16:49
tags:
---
# 介绍
使用`for`进行循环。**RUST**的`for`更像Python的。
# 使用方式
使用`for`循环来遍历集合，相较[[RUST while|while]]和[[RUST loop|loop]]更加安全和高效。
```rust
let a = [1, 2, 3, 4];
for i in a {
	println!("{}", i);
}
```

配合[[RUST Range|range]]进行自定义的循环遍历。
# 相关