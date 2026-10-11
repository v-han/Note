---
updated: 2026-10-09 19:50
created: 2026-10-08 23:36
tags:
---
# 介绍
**Rust**的**RefCell**是**Rust**中用于实现**内部可变性**(Interior Mutability)的**智能指针类型**，即能通过不可变引用仍可以修改内部数据。
# 使用方式
使用`RefCell::new`创建一个**RefCell**，用于管理内部数据。
```rust
let x = RefCell::new(5);
```

使用`borrow`和`borrow_mut`方法来获取内部数据的[[Rust借用和引用|借用]]。
```rust
// 不可变借用,类型为 Ref<T>
let y = x.borrow(); 
// 可变借用，类型为 RefMut<T>
let mut y = x.borrow_mut(); 
```

> [!NOTE]
> 使用RefCell只是将借用检查推到运行时，在运行时仍只能使用一个**可变引用**和多个**不可变引用**。

可以配合[[Rust Rc|Rc指针]]来实现多个引用对一个不可变引用数据的修改。
```rust
let a = Rc::new(RefCell::new(3));
let b = Rc::Clone(&a);

*b.borrow_mut += 1;
```

> [!NOTE]
> 嵌套使用**Rc**和**RefCell**时要避免引用循环会造成内存泄漏，或者使用[[Rust Weak|Weak]]防止引用循环。
> 
> **RefCell**只适用于**单线程模式**。
# 相关