---
updated: 2026-10-01 18:46
created: 2026-10-01 01:43
tags:
---
# 介绍
**Rust**中的动态数组。
**Vector<>** 的数据在内存中是**连续存储**的，且元素必须是**同类型的**。
# 使用方式
使用`Vec::new()`创建一个**Vector**。
```rust
// 此时 v 是空的 Vector，不知道内部元素类型需要标注。
let v: Vec<i32> = Vec::new();
```

使用`vec!`宏来创建一个持有值的**Vector**。
```rust
let v = vec![1, 2, 3];
```

使用`push`方法来为**Vector**添加元素。
```rust
let mut v = Vec::new();
// 通过下面可以判断 v 的类型，因此可以省略。
v.push(3);
```

使用`&`引用的方式或者`get`方法来获取**Vector**中的元素**引用**。
```rust
let num1: &i32 = &v[2];
// 若越界会返回 None
let num2: Option<&i32> = v.get(2);
```
# 相关