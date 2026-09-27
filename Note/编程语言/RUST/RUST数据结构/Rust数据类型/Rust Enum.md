---
updated: 2026-09-27 20:04
created: 2026-09-27 16:58
tags:
---
# 介绍
**Rust**的**枚举类**。
# 使用方式
使用`enum`关键字定义**枚举类**。
```rust
enum Numbers {
	One,
	Two,
	Three,
}
```

可以将**枚举类**的枚举作为**变量的值**、**函数的参数**或**结构体的字段**。
```rust
let num1 = Numbers::one;

fn print_num(num: Numbers) {}

struct num {
	number: Numbers,
}
```

**Rust**的**枚举类**中的枚举还能关联数据。
```rust
enum Message { 
	// 无数据绑定
	Quit,
	// 绑定匿名结构体
	Move { x: i32, y: i32 },
	// 绑定一个数据
	Write(String), 
	// 绑定多个数据
	ChangeColor(i32, i32, i32), 
}
```

和**结构体**一样，枚举类也能使用`impl`定义方法，和[[Rust Struct方法|结构体定义方法]]类似。

可以使用**模式匹配**([[Rust match|match]]、[[Rust if let|if let]])对枚举类进行匹配，执行枚举对应分支
# 相关
[[Rust Option枚举|Option枚举]]