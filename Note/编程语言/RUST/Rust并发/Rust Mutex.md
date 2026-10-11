---
updated: 2026-10-09 20:21
created: 2026-10-09 18:44
tags:
---
# 介绍
**Rust**的**Mutex**(Mutual exclusion，互斥锁)用于对一片**共享数据**进行管理，保证**互斥访问**。
# 使用方式
使用`Mutex::new`创建一个**Mutex**。
```rust
let m = Mutex::new(5);
```

使用`lock`方法来请求**互斥锁**，若有其他线程使用则**阻塞等待**。**Mutex**具有**内部可变性**。
```rust
// 调用 lock 的返回类型是 LockResult<MutexGuard<'_, T>>
let num = m.lock().unwrap();
// 可变类型
let mut num = m.lock().unwrap();
```

多线程同时使用**Mutex**内的数据时应使用**线程安全**的[[Rust Arc|Arc指针]]来。
```rust
let a = Arc::new(Mutex::new(3));
let b = Arc::clone(&a);
```
# 相关
