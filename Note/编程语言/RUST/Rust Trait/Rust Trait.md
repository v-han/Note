---
updated: 2026-10-03 15:30
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

使用`impl`实现**Trait**。
```rust
// 为 NewsArticle 实现 Summary 的 Trait
impl Summary for NewsArticle {
	fn summarize(&self) -> String {
		// 具体实现
	}
}
```

> [!NOTE]
> 需要**Trait**或**类型**其中之一属于当前[[Rust crate|crate]]，才能为该**类型**实现该**Trait**。避免多个crate为同一**类型**实现同一**Trait**。
# 相关
[[Rust Trait Bound|Rust Trait约束]]