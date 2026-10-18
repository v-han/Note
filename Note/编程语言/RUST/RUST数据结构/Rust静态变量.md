---
updated: 2026-10-12 20:45
created: 2026-10-12 20:24
tags:
---
# 介绍
**Rust**的**静态变量**(Static Variables)有固定的内存地址，在整个程序运行期间一直存活。
# 使用方式
使用`static`关键字进行创建**静态变量**，必须用常量表达式来赋值。
```rust
static NUMBER: i32 = 0;
static mut NUMBER2: i32 = 0;
```

可以使用[[Unsafe Rust|unsafe]]进行访问和修改**可变静态变量**。
```rust
unsafe {
	let num = NUMBER2;
	NUMBER2 += 1;
}
```
# 相关
和[[Rust常量|常量]]相比：其内存地址固定，且可以修改。