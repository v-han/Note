---
updated: 2026-10-11 23:50
created: 2026-09-27 19:52
tags:
---
# 介绍
**Rust**中只用于匹配一个模式的**模式匹配**。
# 使用方式
使用`if let`对一个变量进行模式匹配。可以搭配`else`进行其余的模式匹配。
```rust
let num = Some(2);

if let Some(num_args) = num {
	println!("{}", num_args);
} else if let None = num {
	println!("None");
}
```

使用`while let`可以进行循环模式匹配。
# 相关