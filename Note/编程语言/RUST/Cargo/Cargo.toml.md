---
updated: 2026-10-17 18:08
created: 2026-07-31 20:25
tags:
---
# 介绍
**TOML**(Tom's Obvious, Minimal Language)格式，为**Cargo**的配置格式。
# 使用方式
区域标题`[package]`，表示下方内容是用来配置包的。
- **name**：项目名。
- **version**：项目版本。
- **authors**：项目作者。
- **edition**：使用的**RUST**版本。

区域标题`[dependencies]`，表示下方内容是项目的**依赖项**。可以到[crate仓库](https://crates.io/)查看**crate**。Cargo会在构建时自动下载对应的**crate**。
```toml
[dependencies]
rand = "0.10.2"
```

或者使用命令行的方式添加**crate**。
```bash
cargo add csv
```

区域标题`[profile]`，表示下方使用于构建的配置文件。
```toml
# 调试构建的配置文件
[profile.dev]
# 优化级别为 0
opt-level = 0
```
# 相关