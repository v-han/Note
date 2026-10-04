---
updated: 2026-10-03 16:00
created: 2026-10-02 21:06
tags:
---
# 介绍
**Rust**的**泛型**，可以减少重复的定义。
# 使用方式
在**函数**中使用泛型。
```rust
fn funct<T>(arg: &T) -> &T {}
```

在**结构体**中使用泛型。
```rust
// 此时 x, y 必须是一种类型 
// 使用struct MyStruct<T, U> 可同时定义两种泛型
struct MyStruct<T> {
	x: T,
	y: T,
}
```

在**枚举类**中使用泛型，以**Option枚举类**为例。
```
enum Option<T> {
	Some(T),
	None,
}
```

在**方法**中使用泛型，需要在`impl`关键字后接<>。
```rust
// impl MyStruct<i32> 表示定义指定类型的方法
// 不能为泛型和具体类型实现同名方法。
impl<T> MyStruct<T> {
	fn MyFun(&self) -> &T {}
}
```

搭配[[Rust Trait Bound|Trait约束]]为实现特定**Trait**的类型额外提供方法。
```rust
// 为实现 Display Trait 的泛型类型提供额外的方法
impl<T: Display> Pair<T> {
	fn funct(&self) {
		// 具体实现
	}
}
```
# 相关