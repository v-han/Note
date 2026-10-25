---
updated: 2026-08-24 10:27
created: 2026-08-23 13:06
tags:
---
# 介绍
Qt项目的构建流程。
# 构建流程
1. **AUTOMOC**会扫描源文件中的`Q_OBJECT`宏，生成对应的`moc_xxx.cpp`，最后汇总到`mocs_compilation.cpp`。
2. 然后会进行[[UIC]]的操作，将`ui`文件转化为`cpp`文件。
3. 之后编译`mocs_compilation.cpp`、`main.cpp`以及生成的`ui`对应的文件。
4. 将编译的结果进行连接。

可以使用`windeployqt`命令将构建的可执行文件进行Windows的打包。
# 相关