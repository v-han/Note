---
updated: 2026-07-07 00:41
created: 2026-07-07 00:40
tags:
---
# 介绍
以[教学资源](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)中的Step0中的`CMakeList.txt`为例：
```CMake
cmake_minimum_required(VERSION 3.23)

project(Tutorial)

add_executable(hello)
target_sources(hello
  PRIVATE
    HelloWorld.cxx
)
```

`cmake_minimum_required()`：CMake向项目开发者提供的兼容性保证，调用之后CMake将会采用指定版本来构建项目。
`project()`：设置项目名称以及一列复杂的功能。
`add_executable()`：创建一个目标。
`target_sources()`：为`add_executable()`创建的目标关联构建和链接的源文件。
# 相关