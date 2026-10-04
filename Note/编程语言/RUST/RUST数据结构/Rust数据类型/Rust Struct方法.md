---
updated: 2026-09-30 13:36
created: 2026-09-27 01:24
tags:
---
# 介绍
**Rust**中**结构体**的方法。
# 使用方式
使用`impl`关键字为**结构体**定义方法，在之后的`{}`定义其的方法。在定义的方法中若要将**结构体**自身传入参数，可以`self`表示(`&`和`&mut`的方式都可以)。在`impl`内可以使用`Self`表示**原结构体**。
```rust
struct Rectangle {
	width: u32,
	length: u32,
}

impl Rectangle {
	// 定义 Rectangle 的方法
	fn area(&self) -> u32 {
		return self.wigth * self.length;
	}
}

// 相关 main 函数略过
// 方法使用时，rest 会被传入到参数 self
let area = rest.area();
// 以下的调用方式和上面的一致
let area = (&rest).area();
```

> [!NOTE]
> 使用时**Rust**会自动将方法调用实例传给`self`参数，且会自动进行参数的匹配(当**非引用**的实例传入**引用**的参数，会自动转为**引用**的形式)。

若定义的方法第一个参数不是`self`，则被称为该结构体的**关联函数**。
```rust
impl Rectangle {
	// 此时 area 方法是结构体 Rectangle 的关联函数。
	fn area(rect: &Rectangle) -> u32 {
		return rect.wigth * rect.length;
	}
}

// 相关 main 函数略过
// 只能以下的方法调用
let area = Rectangle::area(&rect);
```
# 相关