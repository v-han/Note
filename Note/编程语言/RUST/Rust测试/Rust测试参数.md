---
updated: 2026-10-05 00:58
created: 2026-10-04 23:24
tags:
---
# 介绍
为`Cargo test`中添加参数，使其有更多的功能。
# 使用方式
使用`--show-output`让通过的测试仍能用`println!`宏打印。
```bash
cargo test -- --show-output
```

使用需要测试的函数名作为参数，可以只运行名称匹配的测试函数，即会测试测试函数名中包含指定的字符串的函数。
```bash
// 测试 test_fun() 测试函数
cargo test test_fun
```

可以`#[ignore]`注解让测试函数默认不执行，可用于耗时的代码。使用`--ignored`参数单独运行**被忽略**的代码测试。使用`--include-ignored`参数可一起运行**没有忽略的**和**被忽略的**。
```bash
cargo test -- --ignore
cargo test -- --include-ignored
```
# 相关