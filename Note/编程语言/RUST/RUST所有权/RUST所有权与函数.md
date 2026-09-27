---
updated: 2026-09-25 00:29
created: 2026-09-16 00:06
tags:
---
# 介绍
**Rust**中将值传递给函数和将值传递给变量是类似的，会发生**移动**或**复制**。
# 使用方式
**Rust**的函数执行过程中会发生**移动**或**复制**，将变量的所有权传入函数内部，在走出函数作用域时失去所有权。
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

若要得到传入函数的参数所有权，可以将该变量返回。或则采用[[Rust引用和借用|引用]]的方式。
```rust
fn main() {
	let s1 = String::from("hello");
	// 将变量返回，在得到其的所有权。
	let (s1, len) = cal_length(s1);
	
	println!("The length of {} is {}", s1, len);
}

fn cal_length(s: String) -> (String, usize) {
	let length = s.len();
	
	return (s, length);
}
```
# 相关