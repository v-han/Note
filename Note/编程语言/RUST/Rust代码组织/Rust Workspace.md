---
updated: 2026-10-08 00:18
created: 2026-10-07 23:32
tags:
---
# 介绍
**Rust**的**Workspace**是用于统一管理多个[[Rust Package|package]]的**项目结构**。
由一个根目录的[[Cargo.toml]]文件进行管理，共享同一个**Cargo.lock文件**和**输出目录**。
# 使用方式
使用**Workspace**时项目结构如下。
```
my-project/
├── Cargo.toml          ← Workspace 配置
├── package1/
│   └── Cargo.toml      ← 该 package 的配置
└── package2/
    └── Cargo.toml
```

在根目录的**Cargo.toml**将这些**package**添加到**Workspace**中。
```toml
[workspace]
members = [
    "package1",
    "package2",
]
```

在同一个**Workspace**的**package**之间的依赖仍要显式写出来。
```rust
# 在 package1 中的 cargo.toml 添加依赖
[dependencies]
package2 = { path = "../package2"}
```

> [!NOTE]
> 因为共享同一个**Cargo.lock**，在使用外部依赖时**Rust**会尽量使用同一个版本的依赖(若语义版本兼容则用同一个包，没兼容再使用两个包)。
> 
> 如果一个**package**引入依赖而另一个没有，未引入依赖的无法使用使用这个依赖。

**Workspace**可以使用与普通**package**类似的**Cargo**命令进行构建和测试，可以使用`-p`参数指定某个**package**。
```bash
cargo build -p package1
cargo test -p package1
```
# 相关