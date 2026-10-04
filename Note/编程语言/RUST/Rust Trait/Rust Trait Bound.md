---
updated: 2026-10-03 16:03
created: 2026-10-03 15:16
tags:
---
# 介绍
**Rust Trait约束**是**Rust**中使用实现某种**Trait**的类型作为**函数**的**参数**。
# 使用方式
使用[[Rust泛型|泛型]]的方式表示**函数**需要实现指定**Trait**的**参数**。这里需要注意**泛型**的使用，一个T只能使用一种类型。
```rust
// 要求参数 item 实现 Summary 这个 Trait
fn notify<T: Summary>(item: &T) {
	// 具体实现
}

// 要求参数实现 Summary + Display 多个 Trait
// fn notify<T: Summary + Display>(item: &T)
```

以下为上面使用方式的[[语法糖]]。
```rust
fn notify(item: &impl Summary) {
	// 具体实现
}

// 要求参数实现 Summary + Display 多个 Trait
// fn notify(item: &(impl Summary + Display))
```

使用`where`简化使用多个**Trait约束**函数的定义。
```rust
fn fn notify<T, U>(item: &T, item2: &U) -> i32
where 
	T: Summary + Clone,
	U: Display + Clone,
{
	// 具体实现
}
```

**Rust Trait约束**也能用于返回值类型。
```rust
fn returns_summarizable() -> impl Summary {
	// 具体实现
	// 只能返回一种类型，若返回结果可能有多种类型会报错
}
```

使用**blanket**方式可以为实现某**Trait**的类型实现另一个**Trait**。
```rust
// 为实现 Display Trait 的类型实现 ToString Trait方法
impl<T: Display> ToString for T {
	// 省略
}
```
# 相关