---
updated: 2026-08-24 10:15
created: 2026-08-23 18:43
tags:
---
# 介绍
在编译阶段编译器编译的是`cpp`文件或`h`头文件，而`ui`文件是基于**XML**格式的，需要**UIC**的工具将`ui`文件转化为`h`头文件。
# 作用
生成的`h`头文件有个`setupUi()`方法记录着窗口的组件信息，在主窗口`Widget`的构造函数中会将自己传入到这个方法。
```cpp
Widget::Widget(QWidget *parent): QWidget(parent), ui(new Ui::Widget) {
    ui->setupUi(this);
}
```
# 相关