---
updated: 2026-09-19 01:57
created: 2026-09-16 00:06
tags:
---
# 介绍
**RUST**中将值传递给函数和将值传递给变量是类似的，会发生**移动**或**复制**。
# 使用方式
```rust
fn main() {
	let s1 = String::from("hello");
	
	// 执行该语句后，s1 失效
	let s2 = moveFun(s1);	
}

// 调用过程 s1 的所有权移动到 res_string
// 返回过程 res_string 的所有移动到 s2
fn moveFun(res_string: String) -> String {
	return res_string;
}
```
# 相关