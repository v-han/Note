---
updated: 2026-09-27 19:51
created: 2026-09-27 18:11
tags:
---
# 介绍
**Rust**的分支控制流，使用`match`使一个值与一系列模式进行匹配，并执行对应模式的代码。
# 使用方式
使用`match`对一个变量进行模式匹配，执行对应模式的代码。`match`是自上而下顺序检查每个模式的。
```rust
enum Coin {
    Penny,
    Nickel,
    Dime,
    Quarter(String),
}

// main 函数的部分略过
let coin = Coin::Penny;
// match 会将分支的最后一个表达式返回
let num = match coin {
	Coin::Penny => 1,
	Coin::Nickel => {
		// 分支内部也可以写入语句块，需要用 {} 括起来
	    println!("Nickel");
	    5
    },
    Coin::Dime => 10,
    Coin::Quarter(name) => {
	    // 可以获得枚举中绑定的数据
	    println!("the Quarter from {}", name);
	    25
    },
};
```

> [!NOTE]
> `match`匹配时必须穷举所有的可能。
> 
> 若不需要处理所有的可能模式，可以使用`_`通配符来代替(需要放在最后)没有列出的可能。
# 相关
如果只需要匹配一种模式而忽略其他的模式，可以使用[[Rust if let|if let]]。
[[Rust Enum|Rust枚举类]]