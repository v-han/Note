---
updated: 2026-04-05 01:54
created: 2026-03-31 00:32
tags:
---
# 介绍
执行make命令时，需要有一个Makefile文件告诉make命令怎么样去编译和链接程序。
# 规则
## 使用规则
在要编译的目录下，创建一个Makefile文件(没有后缀)，并按照以下的方式书写：

> [!note]
> 默认情况下，make命令会在当前目录下按顺序寻找文件名为`GNUmakefile`，`makefile`，`Makefile`的文件。
> 在以上三个文件名中推荐使用`Makefile`。最好不要使用`GNUmakefile`，因为这个文件名只能在GNU的make使用。

```Makefile
target ... : prerequisites ...
	recipe
	...
	...
```

**解释**：
`target`：可以是一个object file（目标文件），也可以是一个可执行文件，还可以是一个标签（label）。
`prerequisites`：生成该target所依赖的文件或target。
`recipe`：该target要执行的命令。

> [!note]
> prerequisites中如果有一个以上的文件比target文件要新的话，recipe所定义的命令就会被执行。

> [!tip]
> 可以使用[[Makefile隐式规则|隐式规则]]来简化Makefile内容。
## clean规则
为了便于重新编译和保持文件的清洁，每个Makefile由应该有个clear命令来清理生成的目标文件(`.o`)。
```Makefile
clean :
	rm ...
```

`rm`后面接上要清理的文件。

更加稳健的做法是：
```Makefile
.PHONY : clean
clean :
	-rm ...
```

`.PHONY`表示`clean`是一个[[伪目标]]。
在`rm`之前的`-`表示也许会有一些文件出现问题，但是不用管，继续执行。
# make的工作方式
GNU的make工作执行步骤：
1. 读入所有的Makefile。
2. 读入被include的其他Makefile。
3. 初始化文件的变量。
4. 推导隐式规则，并分析所有规则。
5. 为所有目标文件创建依赖关系链。
6. 根据依赖关系，决定那血目标要重新生成。
7. 执行生成命令。
# 相关
[[CMake]]