---
updated: 2026-08-30 10:54
created: 2026-08-28 18:26
tags:
---
# 介绍
**QWidget**是Qt所有**窗口类**和**控件类**的基类。
可以作为**内嵌窗口**(内嵌到其他窗口内部，需要指定父窗口)和**独立窗口**(独立显示的窗口，无需指定父窗口)。
`Qt`中的窗口类有**3**个，分别是`QWidget`、`QMainWindow`和`QDialog`。
# 使用方式
[[Qwidget常用方法]]。

**QWidget**有以下常用的信号槽。
```cpp
// 最大化显示
void showMaximized();

// 最小化显示
void showMinimized();

// 正常显示
void showNormal();

// 关闭窗口
bool close();
```
# 相关
