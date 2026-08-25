---
updated: 2026-08-01 10:00
created: 2026-07-31 20:25
tags:
---
# 介绍
TOML(Tom's Obvious, Minimal Language)格式，为[[Cargo]]的配置格式。
# 使用方式
区域标题`[package]`，表示下方内容是用来配置包的。
- name：项目名。
- version：项目版本。
- authors：项目作者。
- edition：使用的RUST版本。

区域标题`[dependencies]`，表示下方内容是项目的依赖项。

> [!NOTE]
> 在**RUST**中依赖称作[[crate]]
# 相关