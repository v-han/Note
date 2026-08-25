---
updated: 2026-08-18 18:32
created: 2026-04-07 00:54
tags:
---
# 介绍
CMake中列表文件。
每个CMakeList.txt文件都包含一组命令，用于描述于构建软件项目相关的某些信息或操作。
CMake支持大写、小写和大小写混合书写的命令，但是建议使用小写命令。
# 规则
在根目录下的`CMakeLists.txt`应该要以以下的语句放在开头。
```CMake
# 用于指定 cmake 最低版本。
cmake_minimum_required()
# 用于指定项目名。
project()
```

使用[[add_executable()]]使结果生成一个可执行文件。
```CMake
add_executable(Hello)
```

使用[[target_sources()]]对上面的生成目标添加需要的文件。
```CMake
target_sources(Hello
	PRIVATE HelloWorld.cxx
)
```

可以看看[[CMakeLists例子|入门例子]]。
# 相关
[[CMakeLang]]