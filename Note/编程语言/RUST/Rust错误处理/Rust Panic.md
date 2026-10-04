---
updated: 2026-10-02 16:52
created: 2026-10-02 16:41
tags:
---
# 介绍
**Rust**中**不可恢复的**错误。
出现**panic**后，**Rust**会**打印错误信息**、**展开调用堆栈**和**退出程序**。
# 使用方式
当代码中出现某些危险的行为会导致**panic**。
```rust
let x = [1, 2, 3];
let y = x[99];
```

使用`panic!`显式说明出现**不可恢复**的错误。
```rust
panic!("Error");
```

可修改`RUST_BACKTRACE`环境变量来控制显示的错误信息，需要在**Debug**模式下。
```bash
// 设置为任何不为 0 的值
SET RUST_BACKTRACE=full
```
# 相关