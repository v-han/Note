---
created: 2026-10-08 11:34
updated: 2026-10-08 20:27
tags:
---
# 介绍
**Deref**是**Rust**中用于定义**解引用行为**的**Trait**。
# 使用方式
为自定义数据类型实现**Deref Trait**(只需实现`deref`方法)，即可定义**解引用**行为。
```rust
struct MyBox<T>(T); // new 方法省略

impl<T> Deref for MyBox<T> {
	type Target = T;
	
	// 这里返回的是引用类型
	fn deref(&self) -> &Self::Target {
		&self.0
	}
}
```

当`*`作用于实现了**Deref**的类型时，**Rust**会利用该类型的`deref`方法来实现**解引用**。
```rust
let x = MyBox::new(3);
// *x -> *(x.deref()) -> *(&T) -> T
println!("{}", *x); // *(x.deref())
```

**Rust**会使用**解引用转换**(Deref Coercion)对实现**Deref Trait**的**引用类型**进行自动转换，转换是在编译时完成的。
```rust
let x = MyBox::new(String::from("hello"));
// &MyBox<String> -> &String -> &str
let y: &str = &x;
```

实现**DerefMut Trait**可以实现对可变引用的**解引用**。
```rust
impl<T> DerefMut for MyBox<T> {
    fn deref_mut(&mut self) -> &mut T {
        &mut self.0
    }
}
```

> [!NOTE]
> **解引用转换**使用场景。
> &T -> &U (T: Deref<Target = U>)
> &mut T -> &mut U (T: DerefMut<Target = U>)
> &mut T -> &U (T: Deref<Target = U>)
# 相关