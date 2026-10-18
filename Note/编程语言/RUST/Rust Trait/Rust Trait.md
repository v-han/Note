---
updated: 2026-10-12 23:23
created: 2026-10-02 21:47
tags:
---
# 介绍
**Trait**是**Rust**中定义特定类型所具有的功能。
用于对一系列类型定义一套共享的功能(类似接口？)。
# 使用方式
使用`trait`定义**Trait**。
```rust
trait Summary {
	// 只用声明方法名、参数和放回值类型
	fn summarize(&self) -> String;
	
	// 或者为其提供默认实现
	fn summarize(&self) -> String {
		// 默认实现，可以使用 impl 进行重写
	}
}
```

使用`type`关键字为**Trait**关联类型。
```rust
trait Summary {
	type Item = String;
	
	fn summarize(&self) -> Summary::Item;
}
```

使用`impl`实现**Trait**。
```rust
// 为 NewsArticle 实现 Summary 的 Trait
impl Summary for NewsArticle {
	fn summarize(&self) -> String {
		// 具体实现
	}
}

// 若 NewsArticle 结构体自身有 summarize 方法会优先调用自身的
// 这种情况下需要使用 Summary::summarize(&变量名) 来使用
// 调用关联函数时 <type as Trait>::method() 这样使用
```

使用以下方式让**Trait**依赖另一个**Trait**。
```rust
// 让 PlusDisplay 依赖 fmt::Display
// 要让类型实现 PlusDisplay 时必须也实现 fmt::Display
trait PlusDisplay: fmt::Display {
	// 具体方法，能够实现 fmt::Display 中的方法
}
```

> [!NOTE]
> 需要**Trait**或**类型**其中之一属于当前**crate**(或使用[[Rust Tuple struct|元组结构体]]进行包装)，才能为该**类型**实现该**Trait**。避免多个crate为同一**类型**实现同一**Trait**。
# 相关
[[Rust Trait Bound|Rust Trait约束]]
[[Rust Marker Trait]]
一些**Trait**：[[Rust Deref Trait|Deref Trait]]、[[Rust Drop Trait|Drop Trait]]