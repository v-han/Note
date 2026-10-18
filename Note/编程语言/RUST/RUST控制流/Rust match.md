---
updated: 2026-10-12 00:10
created: 2026-09-27 18:11
tags:
---
# 介绍
**Rust**的分支控制流，使用`match`使一个值与一系列模式进行匹配，并执行对应模式的代码。
# 使用方式
使用`match`对一个变量进行模式匹配，执行对应模式的代码。`match`是自上而下顺序检查每个模式的。
```rust
let s = Some(String::from("Tom"));
// 此处也需要考虑所有权，使用引用防止变量被销毁
let s2 = match &s {
	Some(name) => {
		println!("name is {}", name);
		name
	},
	None => String::from("None"),
}
```

> [!NOTE]
> `match`匹配时**必须穷举**所有的可能。
> 
> 若不需要处理所有的可能模式，可以使用变量接受这个值再进行处理，**或**使用`_`通配符来表示不关心这些值。

使用**匹配守卫**提供进一步的判断。
```rust
match num {
	Some(x) if x % 2 == 0 => println!("{} is even", x),
	Some(x) => println!("{} is odd", x),
	None => (),
}
```
# 相关
如果只需要匹配一种模式而忽略其他的模式，可以使用[[Rust if let|if let]]。
[[Rust Enum|Rust枚举类]]