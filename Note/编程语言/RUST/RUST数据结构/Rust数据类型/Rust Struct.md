---
updated: 2026-10-12 00:03
created: 2026-09-26 16:33
tags:
---
# 介绍
**Rust**的**结构体**(struct)。合理使用**结构体**可以提升代码的可读性，便于维护。
# 使用方式
使用`struct`关键字定义**结构体**以及其名称(使用[[Pascal Case]]命名规范)，在`{}`内定义**结构体**的所有字段的**名称**和**类型**并用逗号分隔(通常保留末尾的逗号，方便后续添加字段)。
```rust
// 定义一个 User 的结构体
struct User {
	username: String,
	age: u32,
}
```

使用**结构体**的名称来实例化一个**结构体**，在`{}`中使用`:`为该**结构体**各个字段赋值。必须为所有定义的字段赋值否则会报错。
```rust
let user = User {
	// 字段的赋值顺序可以和定义的顺序不同
	age: 20,
	username: String::from("Tom"),
}
```

当**结构体**字段名和为其赋值的变量名相同时可以简写。
```rust
let username = String::from("Tom");
let age = 20;

let user = User {
	username,
	age,
}
```

如果使用某个**结构体**实例创建另一个新实例时(即有字段值相同)，可以用**结构体更新**的方式。
```rust
let user2 = User {
	username: String::from("Jack"),
	// 从 user 获得没另外定义的字段的值
	..user,
}
```

使用`.`操作**结构体**的某个字段。只有可变的**结构体**才能改变其字段的值(**一旦**结构体实例是可变的，所有字段都是可变的)。
```rust
let username1 = user.usernam;
```

 可以使用**解构**的方式获取**结构体**的值。
```rust
let User{ username: x, age: y } = user;
println!("user:{}, age:{}", x, y);

// 以下方式效果一致
// let User{ username, age } = user 
// println!("user:{}, age:{}", username, age);
```
# 相关
[[Rust Tuple struct|Rust元组结构体]]
[[Rust Struct方法]]