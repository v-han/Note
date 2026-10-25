---
updated: 2026-08-30 17:12
created: 2026-08-30 16:11
tags:
---
# 介绍
**QLineEdit**是**Qt**中的单行文本输入控件。
# 使用方式
使用`placeholderText()`和`setPlaceholderText()`控制输入框的默认占位字符(未输入显示的字符)。
```cpp
// 获取占位字符
QString placeholderText() const
// 设置占位字符
void setPlaceholderText(const QString &) 
```

使用`alignment()`和`setAlignment()`来控制文本的对齐方式。[[Qt Alignment]]是控制对齐方式的枚举类。
```cpp
// 获取文本的对齐方式
Qt::Alignment alignment() const;
// 获取文本的对齐方式
void setAlignment(Qt::Alignment);
```

使用`echoMode()`和`setEchoMode()`控制[[QLineEdit EchoMode|回显模式]]。
```cpp
// 获取回显模式
QLineEdit::EchoMode echoMode() const
// 设置回显模式
void setEchoMode(QLineEdit::EchoMode)
```

使用`isReadOnly()`和`setReadOnly()`控制文本框的只读属性，使用`isEnabled()`和`setEnabled()`控制文本框的使能属性(无法编辑)
```cpp
// 获取和设置文本框的只读属性
bool isReadOnly() const
void setReadOnly(bool)

// 获取和设置文本框的是否使能
bool isEnabled() const
void setEnabled(bool)
```

**QLineEdit**有以下常用的**信号**。
```cpp
// 当文本框内容改变时，发射该信号
void textChanged(const QString &text)

// 当输入完毕时(enter键 或 失去焦点)，发射该信号
void editingFinished()
```
# 相关