---
updated: 2026-10-01 01:27
created: 2026-09-30 20:57
tags:
---
# 介绍
**Rust**的**模块**，将代码组织成更小更易于管理的单元。
# 使用方式
使用[[Rust Mod|mod]]关键字来声明模块。
```rust
mod models;
```

使用[[Rust路径|路径]]来使用模块中定义的代码，需要注意[[Rust可见性|可见性]]。访问一个模块需要路径上的所有模块均为**可见的**。
```rust
let x = crate::models::user::User;
```

使用[[Rust Use|use]]关键字可以导入模块，不用写出完整的**路径**。
```rust
use crate::models::user::User;

let x = User;
```
# 相关