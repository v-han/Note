---
updated: 2026-10-01 17:45
created: 2026-08-07 22:52
tags:
---
# 介绍
**Rust**的字符串类型，用于存储字符的**集合类型**。
# 使用方式
使用`String::new`创建一个空的字符串类型。
```rust
let s = String::new()
```

使用`String::from()`方法或`to_string`方法利用字符串字面量来创建`String`类型。
```rust
let s = String::from("Hello");
// 普通字符串字面量类型是 &str
let s = "Hello".to_string(); 
```

使用`push_XXX`方法为字符串后拼接字符串。
```rust
// 拼接字符
s.push(' ');
// 拼接字符串字面量
s.push_str("world");
```

使用`+`拼接字符串。
```rust
// 此时 s1 会失去所有权，除第一个变量都要 &str 类型传入
let s3 = s1 + &s2;
// 较长的字符串凭借可以使用以下宏的形式
// 和 let s3 = s1 + ":" &s2;
let s3 = format!("{s1}:{s2}");
```

> [!NOTE]
> **Rust**的**字符串**不允许使用索引访问(无法确定字符边界)，只能使用[[Rust String Slice|字符串切片]]的方式。

使用`chars`和`bytes`获取字符串的字符或字节数组。
```rust
// 返回类型是一个迭代器
for c in "123".chars() {}
for b in "123".bytes() {}
```
# 相关