---
updated: 2026-08-01 10:07
created: 2026-08-01 10:00
tags:
---
# 介绍
RUST的依赖，可以到[这里](https://crates.io/)下载依赖。
# 使用方式
将依赖的名称和版本添加到`[dependencies]`下。
```toml
[dependencies]
rand = "0.10.2"
```

> [!NOTE]
> 写版本的时候可以添加`^`符号表示可以使用兼容版本。

使用构建指令后会自动到网址下载对应的依赖。
```bash
cargo build
```
# 相关