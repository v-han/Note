---
updated: 2026-08-18 18:32
created: 2026-04-05 01:39
tags:
---
# 介绍
C语言的构建工具。
[CMake的官方教程](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)
可以在[这里](https://cmake.org/cmake/help/latest/_downloads/cbf94aae014abbf165268dcf2faa3608/cmake-4.3.1-tutorial-source.zip)下载到教学资源。
# 使用方式
使用`cmake -S`命令指定项目的根目录，这个目录下要包含一个[[CMakeLists书写要求|CMakeLists.txt]]文件。
```bash
cmake -S <dir>
```

> [!tip]
> 在未指定项目的根目录时，会默认选择当前目录作为项目的根目录，因此不需要额外执行这个命令。

使用`cmake -B <dir>`命令在指定的目录下创建一个构建系统目录，CMake会将构建系统的文件和构建系统运行时生成的构建产物输出到该目录。
```bash
cmake -B build
```

在当前目录下生成一个叫`build`的构建系统目录。

> [!note]
> 可以使用`cmake -G <构建系统> -B build`使用指定的构建系统。
> 
> 在不指定构建系统时，cmake会自动寻找合适的构建系统。
> 在Windows环境下，cmake会默认使用`nmake`(Visual Studio的工具链)作为构建系统。因此在MinGW的环境下要使用`cmake -G "MinGW Makefiles" -B build`。

使用`cmake --build`使用指定构建系统。
```bash
cmake --build build
```

使用`build`构建目录对项目进行构建。
# 相关