---
updated: 2026-10-07 02:02
created: 2026-10-06 18:37
tags:
---
# 介绍
**Rust**的**迭代器**(Iterator)是实现了**Iterator Trait**的类型，用于依次对一系列元素进行某些操作。
# 使用方式
对实现`iter`方法了集合使用`iter`方法可以得到该集合的**迭代器**。
```rust
let v = vec![1, 2, 3];

// 不可变引用的迭代器
let v_iter = v.iter();
// 获得所有权的迭代器
let v_into_iter = v.into_iter();
// 可变引用的迭代器
let v_iter_mut = v.iter_mut();
```

使用**迭代器**可以遍历集合元素。
```rust
for x in v_iter {}
```

使用`next`方法可以依次获取**迭代器**中的元素。调用时会使**迭代器**的内部状态向后推进，因此需要将**迭代器**声明为可变的。除`next`外消耗迭代器的方法被称为**消耗性适配器**(Consuming Adaptors)，例如`count`、`sum`和`collect`等。
```rust
let mut v_iter = vec![1, 2, 3].iter();

if let Some(x) = v_iter.next() {
	println!("{}", x);
}
```

使用`map`方法配合[[Rust闭包|闭包]]可以为集合元素进行同一操作。这些对**迭代器**进行转换、过滤等操作，并返回新的**迭代器**的方法称为**迭代器适配器**(Iterator Adaptors)，除`map`以外还有`filter`等。
```rust
let v1 = vec![1, 2, 3];
// 迭代器是惰性的，使用 map 只会返回新的迭代器
// 只有消耗迭代器的元素时才会修改原来的值，例如 next()
let iter = v1.iter().map(|x| x + 1)
// Vec<_> 的 _ 表示让编译器根据 collect() 推导类型
let v2: Vec<_> = v1.iter().map(|x| x + 1).collect();
```
# 相关
**Rust**的**迭代器**的性能略优于[[Rust for|for循环]]。