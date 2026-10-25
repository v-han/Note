---
updated: 2026-08-28 20:48
created: 2026-08-28 19:15
tags:
---
# 介绍
**QWidget**窗口操作相关的方法。
# 使用方式
使用以下的方法设置窗口的几何信息。
```cpp
// 获取几何位置信息。
const QRect &geometry() const;
// 设置几何位置信息。
void setGeometry(int x, int y, int w, int h);
void setGeometry(const QRect &);

// 获取窗口的几何信息。
QRect frameGeometry() const

// 重新设置窗口的位置
void move(int x, int y);
void move(const QPoint &);
```

> [!NOTE] 
> 具体的几何含义可以看下图。左上角表示屏幕的左上角。
> ![[Pasted image 20260828190826.png]]

使用以下的函数来设置窗口的大小。
```cpp
// 设置窗口尺寸
QSize size() const
void resize(int w, int h);
void resize(const QSize &);

// 设置最大尺寸
QSize maximumSize() const;
void setMaximumSize(const QSize &);
void setMaximumSize(int maxw, int maxh);

// 设置最小尺寸
QSize minimumSize() const;
void setMinimumSize(const QSize &);
void setMinimumSize(int minw, int minh);

// 设置固定尺寸
void setFixedSize(const QSize &s);
void setFixedSize(int w, int h);

// 单独设置窗口的高度
int height() const;
int minimumHeight() const;
int maximumHeight() const;

void setFixedHeight(int h);
void setMaximumHeight(int maxh);
void setMinimumHeight(int minh);

// 单独设置窗口的宽度
int width() const;
int minimumWidth() const;
int maximumWidth() const;

void setFixedWidth(int w);
void setMaximumWidth(int maxw);
void setMinimumWidth(int minw);
```

使用`windowTitle()`和`setWindowTitle()`来设置窗口的标题。
```cpp
// 获取窗口的标题
QString windowTitle() const;
// 设置窗口的标题
void setWindowTitle(const QString &);
```

使用`windowIcon()`和`setWindowIcon()`来设置窗口的图标。
```cpp
// 获取窗口的图标
QIcon windowIcon() const;
// 设置窗口的图标
void setWindowIcon(const QIcon &icon);
```

使用`paraentWidget()`和`children()`获取父控件和子控件列表。
```cpp
// 获取父控件
QWidget *QWidget::parentWidget() const
// 获取子控件列表
const QObjectList &QObject::children() const
```
# 相关

