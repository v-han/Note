---
updated: 2026-10-08 21:10
created: 2026-10-08 20:16
tags:
---
# 介绍
**Drop**是**Rust**中用于定义值被**销毁**时需要执行的**清理操作**。
**Rust**会为走出作用域的值自动执行**Drop操作**。
# 使用方式
为自定义类型实现**Drop Trait**(只需实现`drop`方法)，即可定义**销毁**行为。
```rust
impl<T> Drop for MyBox<T> {
	// 需要传入可变引用
	fn drop(&mut self) {
		// Rust 会自动销毁字段，字段销毁会清理对应数据
		println!("MyBox has been dropped");
	}
}

// 在变量走出作用域时，Rust会自动调用 x.drop() 方法
```

> [!NOTE]
> **Rust**的**Drop**顺序与变量的创建顺序**相反**。
> 且**Rust不允许**显式调用`drop`方法，只能使用`std::mem::drop`函数。
> ```rust
> // 获得所有权，并销毁该值
> drop(x);
> ```
# 相关