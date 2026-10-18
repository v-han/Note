---
updated: 2026-10-14 00:37
created: 2026-10-13 12:58
tags:
---
# 介绍
**Rust**的**宏**(Macro)是一种元编程机制，可以通过编写宏来生成代码。**宏**通常在编译过程中展开，生成的代码会参与后续编译。
**Rust**的**宏**主要为**声明式宏**(Declarative Macros)和**过程宏**(Procedural Macros)两大类。
# 使用方式
**声明式宏**使用`macro_rules!`定义，通过**模式匹配**接收不同的输入并生成对应的代码。
```rust
#[macro_export] // 导出宏，能够让其他
macro_rules! vec {
	// $() 表示重复，$x:expr 表示任意 Rust 表达式并用 $x 接收
	// * 表示这个模式可以重复，, 表示用逗号分隔
    ($($x:expr),* $(,)?) => {
        {
            let mut temp_vec = Vec::new();
            $(
                temp_vec.push($x);
            )*
            temp_vec
        }
    };
}
```

**过程宏**主要有**派生宏**(Derive Macros)、**属性宏**(Attribute-like Macros)、**函数式宏**(Function-like Macros)(后面懒得写了)。
# 相关