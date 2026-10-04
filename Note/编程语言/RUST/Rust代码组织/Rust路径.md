---
updated: 2026-10-01 01:14
created: 2026-10-01 00:19
tags:
---
# 介绍
**Rust**中使用模块时，需使用路径来描述其位置。
# 使用方式
使用**绝对路径**来描述位置，从**crate根**开始描述。
```rust
let x = crate::models::user::User;
```

使用**相对路径**来描述位置，使用`self`和`super`表示从当前模块或从父模块开始，`self::`在大部分情况下可以省略。
```rust
let x = super::models::user::User;
```

若要使用**library crate**中的模块，需要使用[[Cargo.toml|package]]中的包名。
```rust
let x = my_project::models::user::User;
```
# 相关