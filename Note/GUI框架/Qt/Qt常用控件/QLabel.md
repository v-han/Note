---
updated: 2026-08-30 16:23
created: 2026-08-30 10:44
tags:
---
# 介绍
**QLabel**是**Qt**中用于在用户界面显示文本或图片的组件。
# 使用方式
使用`text()`和`setText()`来控制标签的文本。
```cpp
// 获取标签的文本
QString text() const;
// 设置标签的文本
void setText(const QString &text);
```

使用`alignment()`和`setAlignment()`来控制标签文本的对齐方式。[[Qt Alignment]]是控制对齐方式的枚举类。
```cpp
// 获取文本的对齐方式
Qt::Alignment alignment() const;
// 获取文本的对齐方式
void setAlignment(Qt::Alignment);
```

使用`wordWrap()`和`setWordWrap()`来控制标签文本的自动换行。
```cpp
// 获取自动换行状态
bool wordWrap() const;
// 设置自动换行状态
void setWordWrap(bool on);
```

使用`pixmap()`和`setPixmap()`将`QPixmap`对象设置到标签上，使标签显示图片。
```cpp
// 获取显示的图片
const QPixmap *pixmap() const;
// 设置显示的图片
void setPixmap(const QPixmap &pixmap);
```
# 相关