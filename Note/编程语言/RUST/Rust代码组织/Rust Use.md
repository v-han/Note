---
updated: 2026-10-01 01:33
created: 2026-10-01 01:20
tags:
---
# 介绍
**Rust**中用于导入模块中的元素到当前**作用域**。
# 使用方式
使用`use`导入模块中的元素，需要注意[[Rust可见性|可见性]]。
```rust
use crate::models::user::User;

let x = User;
```

使用`as`为导入的元素起别名，防止导入元素名相同(也可以在使用时加上父级模块)。
```rust
use crate::models::user::User as User1;
```

如果要导入同一模块下的多个元素可以使用以下方法。
```rust
use models::user::{User, User2};
// 导入所有元素
use models::user::*;
```
# 相关