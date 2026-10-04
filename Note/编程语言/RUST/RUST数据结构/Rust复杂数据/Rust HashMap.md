---
updated: 2026-10-03 00:36
created: 2026-10-01 18:12
tags:
---
# 介绍
**Rust**中的**HashMap**，用于存储**键值对**且一个**HashMap**的**键值对**类型必须相同。
# 使用方式
使用`HashMap::new()`来创建一个空的**HashMap**。
```rust
let mut scores: HashMap<String, i32> = HashMap::new();
```

使用`insert`方法来为**HashMap**添加**键值对**，若已存在这个**key**则会覆盖**value**。
```rust
let mut scores = HashMap::new();

scores.insert(String::from("Blue"), 90);
// 此时 String::from("Blue") 的 value 是 80
scores.insert(String::from("Blue"), 80);
```

使用`entry`方法来为HashMap添加键值对，若已存在这个key则不插入。
```rust
// 若有无此 key 则插入，否则将 value 返回
scores.entry(String::from("Blue")).or_insert(80);
```

使用`get`方法根据**key**获取**HashMap**中的value。
```rust
// 返回类型是 Opton<&V> ，是 value 的引用
let score = scores.get("Blue");
```

可以使用**元组**的方式遍历**HashMap**。
```rust
for (key, value) in &scores {}
```

所有权Trait
# 相关


