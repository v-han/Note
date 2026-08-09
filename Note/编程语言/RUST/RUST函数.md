---
updated: 2026-08-04 14:32
created: 2026-08-03 14:42
tags:
---
# 介绍
**RUST**的函数。
# 使用方式
使用`fn`定义函数，函数名的命名使用[[Snake Case]]命名规范。
```rust
fn the_function() {
	println!("the function");
}
```

> [!TIPS]
> **RUST**的函数不需要提前声明。

要让函数使用参数时要指出每个参数的类型，多个参数使用逗号分开。
```rust
fn the_function(x: i32) {
	println!("x is {}", x)
}
```

使用`->`符号后面声明函数的返回值类型。
```rust
fn the_function() -> i32 {
	3
}
```

> [!NOTE]
> 在**RUST**里，返回值就是函数体里最后一个表达式。若要提前返回，可以和其他语言一样使用`return`关键字。

# 相关