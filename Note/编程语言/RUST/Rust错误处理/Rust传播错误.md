---
updated: 2026-10-02 20:36
created: 2026-10-02 17:51
tags:
---
# 介绍
**Rust**中将错误返回，由调用该函数的代码处理错误。
# 使用方式
让函数的调用返回[[Rust Result|Result]]枚举。若无错误则继续执行，若出现错误则将错误返回交由上级处理。
```rust
fn read_name_from_file() -> Result<String, io::Error> {
	let name_file = File::open("Hello.txt");
	let mut name_file match file_res {
		// 若正常则继续执行
		Ok(file) => file,
		// 出现错误直接返回，交由上级处理
		Err(e) => return Err(e),
	}
	
	let mut name = String::new();
	match name_file.read_to_string(&mut name) {
		Ok(_) => Ok(name),
		Err => Err(e),
	}
}
```

使用`?`运算符可以简化上面的操作，如果操作成功会**解包Ok**并继续执行，若操作失败会返回**Err**。上面的操作可以简化为这样。
```rust
fn read_name_from_file() -> Result<String, io::Error> {
	// 相当于上面第一个 match 处代码
	let mut name_file = File::open("Hello.txt")?;
	
	// 相当于上面第二个 match 处代码
	let mut name = String::new();
	name_file.read_to_string(&mut name)?;
	
	// 使用链式调用可以使代码更加简洁
	// let mut name  = String::new();
	// File::open("Hello.txt")?.read_to_string(&mut name)?;
	
	Ok(name);
}
```

> [!NOTE]
> 使用`?`时函数的返回值类型需要为**Result**或**Option**，且**Result**的**错误类型**能够兼容。或实现了**FromResidual**的函数。
# 相关