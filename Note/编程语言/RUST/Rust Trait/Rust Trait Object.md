---
created: 2026-10-11 18:51
updated: 2026-10-11 23:21
tags:
---
# 介绍
**Rust**中的**Trait对象**是一种用于实现**动态分发**(Dynamic Dispatch)的机制，可以用统一类型来存储和使用实现了同一[[Rust Trait|Trait]]的值。
# 使用方式
使用`dyn`关键字可以创建Trait对象。
```rust
// Button 和 Text 的定义省略，两个都是实现了 Draw Trait 的类型
let component: Vec<Box<dyn Draw>> = vec![
	Box::new(Button),
	Box::new(Text),
];
```

> [!NOTE]
> `dyn`是动态大小类型，不能直接创建局部变量，只能以指针的方式使用。
> ```rust
> let button = Button;
> let p1: &dyn Draw = &button;
> ```
# 相关