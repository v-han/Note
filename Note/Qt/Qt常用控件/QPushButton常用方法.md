---
updated: 2026-08-29 13:45
created: 2026-08-29 13:45
tags:
---
# 介绍
**QPushButton**的常用方法。
# 使用方式
使用`text()`和`setText()`来控制按钮上的文本。
```cpp
// 获取文本
QString text() const
// 设置文本
void setText(const QString &text)
```

使用`icon()`和`setIcon()`来控制按钮上的图标。
```cpp
// 获取图标
QIcon icon() const
// 设置图标
void setIcon(const QIcon &icon)
```

使用`shortcut()`和`setShortcut()`来控制按钮的快捷键。
```cpp
// 获取按钮的快捷键
QKeySequence shortcut() const;
// 设置按钮的快捷键
void setShortcut(const QKeySequence &key);

```

使用`styleSheet()`和`setStyleSheet()`来控制按钮的样式表。
```cpp
// 这其实是 QWidget 类的方法
// 获取样式表
QString styleSheet() const
// 设置样式表
void setStyleSheet(const QString &styleSheet)
```

使用以下的方法来控制按钮的自动重复，即按住按钮不放按钮自动继续触发`click()`信号。
```cpp
// 开启/关闭按钮的自动重复功能
void setAutoRepeat(bool);
bool autoRepeat() const;

// 设置初始延迟时间（毫秒）。即从按下按钮到开始自动重复的等待时长。
void setAutoRepeatDelay(int);
int autoRepeatDelay() const;

// 设置重复间隔时间（毫秒）。即开始自动重复后，两次 clicked() 信号之间的时间间隔。
void setAutoRepeatInterval(int);
int autoRepeatInterval() const;
```
# 相关