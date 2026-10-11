---
updated: 2026-10-09 18:44
created: 2026-10-09 15:53
tags:
---
# 介绍
**Rust**的**多线程**让**Rust**的程序的不同部分能够**并发**执行。
**Rust**的**所有权**和**类型系统**能够在编译时防止**并发**错误。
# 使用方式
使用`thread::spawn`函数创建一个新线程，其参数为一个[[Rust闭包|闭包]]，即要运行的代码。
```rust
thread::spawn(|| {
	for i in 0..9 {
		println!("{}", i);
		// 线程暂停
		thread::sleep(Duration::from_millis(1));
	}
});
```

> [!NOTE]
> **Rust**主线程完成时，其他的进行无论有没有执行完都会被结束。
> 且并发时无法保证线程运行的顺序。

使用**JoinHandle**的`join`方法，可以阻塞当前线程，直到该句柄关联的线程执行完毕。
```rust
// thread::spawn 的返回类型时 JoinHandle<()>
let handle = thread::spawn(|| {
	// 代码省略
});

// join 的返回值是一个 Result，若发生 panic 返回 Err
// 使用 join 会阻塞当前线程，直到 handle 关联的线程结束
handle.join().unwrap();
```

在新线程中使用当前环境的引用时无法保证**被引用**的对象在线程执行期间一直存在，使用`move`为闭包获取所有权，从而避免**部分生命周期问题**。
```rust
let handle = thread::spawn(move || {
	// 将所有权移到此处，外部环境就失去所有权
	// 代码省略
});
```
# 相关
线程间使用[[Rust Channel|Channel]]进行消息通信，或者使用[[Rust Mutex|Mutex]]的方式通过互斥锁进行内存共享。
