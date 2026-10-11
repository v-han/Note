---
created: 2026-10-09 17:41
updated: 2026-10-09 21:46
tags:
---
# 介绍
**Rust**中**Channel**用于线程之间的**信息传递**。
# 使用方式
使用`std::sync::mpsc`模块(Multiple Producer, Sinple Consumer)下的channel方法来创建**通道**。
```rust
// 返回一个元组，分别是发生者 Sender<> 和接受者 Receiver<>。
let (tx, rx) = mpsc::channel();
```

对于**发送者**使用`send`方法发送信息。
```rust
let x = String::from("hello");
// 返回值是 Result，若发送失败会返回发送错误 SendError
tx.send(x);
```

对于**接受者**使用`recv`方法接受消息。
```rust
// recv 会阻塞当前进程，直到收到一个值，若所有发送者都关闭返回错误
let rec_x = rx.recv().unwrap();
// try_recv 会立即返回 Result，有信息则用 Ok 包含信息，否则错误
let rec_x = rx.try_recv().unwrap();
```

或者使用`for`循环持续接受信息，接受方会持续接受数据，直到发送方都被销毁且通道中没有数据。
```rust
for i in rx {
	println!("{}", i)
}
```

> [!NOTE]
> 对于发送的值，发送方会丢失**所有权**，接受方会获得**所有权**。
> 
> 可以将**发送者**或**接受者**以闭包捕获的方式移动到别的线程中实现**线程通信**。

可以使用`Clone`的方式克隆**发送者**，实现多个**发送者**发送信息。
```rust
let tx2 = tx.clone();
```
# 相关
[[Rust Send Trait|Send Trait]] 
[[Rust Sync Trait|Sync Trait]]