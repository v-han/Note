---
updated: 2026-10-02 17:50
created: 2026-10-02 16:53
tags:
---
# 介绍
**Rust**中用于处理**可恢复**的错误的**枚举类**。
# 使用方式
`Result`是**Rust**的一个**枚举类**，其定义如下。
```rust
enum Result<T, E> {
	Ok(T),
	Err(E),
}
```

使用[[Rust match|match]]对其进行**模式匹配**。
```rust
let file1_res: Result<File> = File::open("Hello.txt");

let file1 = match file1_res {
	Ok(file) => file,
	Err(error) => panic!("open the file error"),
}
```
# 相关
[[Rust Unwrap和Expect]]