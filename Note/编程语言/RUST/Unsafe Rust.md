---
created: 2026-10-12 18:55
updated: 2026-10-12 20:50
tags:
---
# 介绍
**Rust**的**Unsafe Rust**允许开发者绕过编译器无法验证的部分安全检查，并由自行保证这些操作的正确性。
# 使用方式
使用`unsafe`关键字标记不安全操作。
```rust
// 不安全代码块
unsafe {}
// 不安全函数
unsafe fn unsafe_fun() {}
// 不安全 Trait
unsafe trait unsafe_trait {}
// 实现不安全 Trait
unsafe impl unsafe_trait for MyStruct {}
```

以下为**不安全Rust**下才能进行的行为：解引用[[Rust原始指针|原始指针]]。
```rust
unsafe {
	let r1: *const i32 = &raw const num;
	let num = *r1
}
```

使用`extern`调用外部代码。
```rust
// 调入 C 标准库的 abs 函数
unsafe extern "C" {
	// 使用这个函数仍需 unsafe 包围
	fn abs(x: i32) -> i32;
	// 确保其安全可以不用 unsafe 包围
	// safe fn abs(x: i32) -> i32;
}
```

访问或修改**可变**[[Rust静态变量|静态变量]]。
```rust
static mut COUNTER: u32 = 0;

unsafe {
	COUNTER += 1;
}
```

定义或使用**不安全**的**Trait**。访问**Union**的字段。

> [!NOTE]
> 为了安全的使用**Unsafe**，应该对不安全的代码进行封装。
> ```rust
> fn normal_fun() {
> 	unsafe {
> 		// 不安全的操作或方法
> 	}
> }
> ```
# 相关