---
updated: 2026-10-01 00:18
created: 2026-09-30 22:51
tags:
---
# 介绍
**Rust**中用于声明**模块**的关键字。
# 使用方式
使用`mod`直接声明模块，后面接`{}`使用内联的方式直接定义**模块**。
```rust
mod models {
	// 模块中内容
}
```

使用`mod`声明外部模块，模块对应的文件或目录位置由其父模块的位置决定。
```rust
// 要求 src 目录下有 models.rs 文件
// 或 src 目录下有 models 目录，且目录里有 mod.rs 文件
mod models;

// 在 models 模块下加子模块，以下代码写到 models 模块下
// 要求 src/models 目录下有 user.rs 文件
// 或 src/models 目录下有 user 目录，且目录里有 mod.rs 文件
mod user;
```
# 相关