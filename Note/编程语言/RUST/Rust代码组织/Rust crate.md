---
updated: 2026-10-05 21:10
created: 2026-09-30 20:56
tags:
---
# 介绍
**Rust**的**编译单元**。
# 使用方式
**Rust**的**crate**分为以下两种：
1. **二进制crate**(binary crate)：可执行的，必须有main函数。以`src/main.rs`为编译入口。
2. **库crate**(library crate)：无法执行，定义一些功能。以`src/lib.rs`为编译入口。

> [!NOTE]
> 一般将项目的**逻辑部分**放在`lib.rs`下，让`main.rs`只负责调用命令行的解析、设置配置调用`lib.rs`的**run**函数以及处理**run**函数的错误。
# 相关