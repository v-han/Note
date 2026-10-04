---
updated: 2026-10-03 17:07
created: 2026-09-24 23:51
tags:
---
# 介绍
**Rust**的**借用**，获取变量的**引用**而不获取其的**所有权**。
# 使用方式
在类型使用`&`表示是**引用数据类型**，在变量前使用`&`表示取该变量的引用。
```rust
let s1 = String::from("hello");
// 由于类型可以自动推导，这里这里以写为 let s2 = &s1
let s2: &String = &s1;
```

在函数的使用中同理，不使用**借用**在函数编写上会比较繁琐。
```rust
fn main() {
	let s1 = String::from("hello");
	// 此时是 s1 不会失去所有权。
	let len = cal_length(&s1);
	println!("The length of {} is {}", s1, len);
	
	let (s1, len) = cal_length2(s1);
	println!("The length of {} is {}", s1, len);
}

fn cal_length(s: &String) -> usize {
	return s.len();
}

// 不使用借用，s 会在走出作用域被清理，需要将其返回
fn cal_length2(s: String) -> (String, usize) {
	return (s, s.len());
}
```

> [!NOTE]
> 和[[Rust变量|普通变量]]一样，借用的变量也是默认不可变的。若要能通过引用来控制变量需使用[[Rust可变引用|可变引用]]。

一个变量不能同时拥有**被引用权**和**修改权**，被引用后可以通过**可变引用**来修改。
```rust
let mut x = 3;
let y = &x;

// 下面代码是错误的
// x += 1;
println!("{}", y);
// 若在 y 不再被使用，Rust会回收这次借用，则可以修改 x
x += 1;
```

使用**引用**时，原变量必须一直有效。**Rust**禁止**悬空引用**。
```rust
fn get_String() -> &String {
	let s = String::from("hello");
	return &s
	// s 走出其作用域失效了，其的引用也失效了
}

// 以下的代码会出现报错
let s = get_String();
```
# 相关
[[Rust解引用]]
[[Rust生命周期]]
[[Rust String Slice|Rust字符串切片]]
