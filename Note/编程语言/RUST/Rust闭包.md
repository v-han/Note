---
updated: 2026-10-06 15:18
created: 2026-10-05 21:11
tags:
---
# 介绍
**Rust闭包**(Closures)是一种捕获其所在环境中变量的**匿名函数**。
**闭包**不需要像正常函数一样标注**参数**和**返回值**类型，通常很短以便编译器能够推导出**参数**和**返回值**类型。
# 使用方式
使用`||`表示一个**闭包**，在`||`中表示**闭包**的参数，后面的是其逻辑。
```rust
// 定义一个闭包，并赋值给一个变量
let example_closure = |x| x;
// 也可以加上类型注解
// let example_closure = |x: &str| -> &str { x };

// 这里编译器将其推导为 &str 类型，以后不能用其他类型
let res = example_closure("123");
```

使用**闭包**时可以**捕获**当前环境的变量。
```rust
let x = 1;
// 捕获 x 变量
let example_closure = |y| x + y;

let res = example_closure(2)
```

根据捕获的变量的使用方式，捕获方式分为**不可变引用**、**可变引用**和**获取所有权**。**闭包**会为其自动实现对应的[[Rust闭包 Trait|Trait]]。
```rust
// 捕获不可变引用
let clos1 = || println!("{}", x);
// 捕获可变引用，这里 x 需要是可变变量
let clos2 = || x += 1; // 会自动捕获可变引用
// 获取所有权，如果实现 Copy Trait 这里是捕获副本
let clos3 = move || x + 1;
```

闭包捕获的一般都是**引用**，需要注意[[Rust生命周期|生命周期]]。对于闭包这种**隐藏类型**如果需要明确表达返回的闭包不能超过输入引用的**生命周期**需要显式写出。
```rust
// 返回实现 Fn() -> String 的隐藏类型，并要求生命周期不超过 'a
fn make_a_cloner<'a>(s: &'a str) -> impl Fn() -> String + 'a {
    move || s.to_string()
}
```
# 相关