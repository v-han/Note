---
updated: 2026-10-04 21:07
created: 2026-10-04 20:45
tags:
---
# 介绍
**Rust**的[[断言]]，在测试中判断某个条件是否符合预期。
# 使用方式
使用`assert!`宏接受一个**布尔类型**作为参数，如果值为`true`通过测试否则会触发[[Rust Panic|panic]]。
```rust
assert!(res);
```

使用`assert_eq!`宏和`assert_ne!`宏(需要实现**PartialEq**和**Debug**两个[[Rust Trait|Trait]])判断**相等性**和**不相等性**，断言失败时会打印两个值。
```rust
// 相等认为是逻辑正确
assert_eq!(res, 2);
// 不相等认为是逻辑正确
assert_ne!(res, 2);
```

为`assert!`添加额外的参数，在断言失败后出现额外的自定义信息。
```rust
assert!(res, "发生了错误");
```

添加`#[should_panic]`表示测试应该发生**panic**，没发生认为没通过测试。
```rust
#[test]
#[should_panic]
fn test_fun() {
	// 具体实现
}

// 可以加上 expected 期待指定的 panic 错误。
#[should_panic(expected = "xx错误")]
```
# 相关