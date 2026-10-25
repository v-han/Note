---
updated: 2026-09-04 23:59
created: 2026-08-29 13:23
tags:
---
# 介绍
**QPushButton**是**Qt**中的按钮控件，用于响应用户的点击然后执行对应的操作。继承自[[QAbstractButton]]。
# 使用方式
[[QPushButton常用方法]]。

**QPushButton**有以下常用的信号。
```cpp
// 当按钮被点击(按下并释放)，发送该信号
// 对于 QCheckBox 和 QRadioButton 可以使用 clicked 参数判断是否被选中。
void clicked(bool checked = false);

// 当按钮被按下时，发送该信号
void pressed();

// 当按钮被抬起时，发送该信号
void released();
```
# 相关