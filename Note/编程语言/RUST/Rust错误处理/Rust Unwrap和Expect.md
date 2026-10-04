---
updated: 2026-10-02 17:50
created: 2026-10-02 17:42
tags:
---
# 介绍
Rust中用于提取**Option**或**Result**内部的值。
# 使用方式
使用`unwrap`方法提取**Option**或**Result**内部的值，若是**None**或**Err**程序会[[Rust Panic|panic]]终止。
```rust
let file1_res: File = File::open("Hello.txt").unwrap();
```

使用`expect`方法提取**Option**或**Result**内部的值，若是**None**或**Err**程序会**panic**终止并**输出**指定的错误。
```rust
let file1_res: File = File::open("Hello.txt").expect("File not found");
```
# 相关