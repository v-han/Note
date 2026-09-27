---
updated: 2026-09-26 18:39
created: 2026-09-24 23:51
tags:
---
# 介绍
**Rust**的借用，获取变量的**引用**而不获取其的**所有权**。
# 使用方式
在类型使用`&`表示是引用数据类型，在变量前使用`&`表示取该变量的引用。
```rust
let s1 = String::from("hello");
// 由于类型可以自动推导，这里这里以写为 let s2 = &s1
let s2: &String = &s1;
```

在函数的使用中同理。
```rust
fn main() {
	let s1 = String::from("hello");
	// 此时是 s1 不会失去所有权。
	let len = cal_length(&s1);

	println!("The length of {} is {}", s1, len);
}

fn cal_length(s: &String) -> usize {
	return s.len();
}
```

> [!NOTE]
> 和[[Rust变量|普通变量]]一样，借用的变量也是默认不可变的。若要能通过引用来控制变量需使用[[Rust可变引用|可变引用]]。
> 在任何一个作用域中，只能存在一个可变引用**或**多个不可变引用。

使用引用时，原变量必须一直有效。**Rust**编译器会对这种**悬空引用**进行报错。
```rust
fn main() {
	// 以下的代码会出现报错
	let s = get_String();
}

fn get_String() -> &String {
	let s = String::from("hello");
	return &s
	// s 走出其作用域失效了，其的引用也失效了
}

```
# 相关
[[Rust String Slice|Rust字符串切片]]