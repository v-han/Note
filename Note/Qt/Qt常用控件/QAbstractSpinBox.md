---
updated: 2026-09-08 21:29
created: 2026-09-08 20:57
tags:
---
# 介绍
**Qt**中微调框的的**抽象类**。
# 使用方法
使用以下的方法来控制微调框的值的控制。
```cpp
// 获取和设置当前值
int value() const
void setValue(int val)

// 获取和设置最大值
int maximum() const
void setMaximum(int max)

// 获取和设置最小值
int minimum() const
void setMinimum(int min)

// 一次设置最大值和最小值
void setRange(int minimum, int maximum)
```

使用`singleStep()`和`setSingleStep()`控制微调框的步长。
```cpp
// 获取步长
int singleStep() const
// 设置步长
void setSingleStep(int val)
// 使用 QDoubleSpinBox 使用这里的类型是 Double
```

使用`wrapping()`和`setWrapping()`控制微调框的循环。
```cpp
// 获取循环状态
bool wrapping() const
// 设置循环状态
void setWrapping(bool w)
```

可以使用以下的方法添加微调框的前缀和后缀。
```cpp
QString prefix() const
void setPrefix(const QString &prefix)

// 获取和设置后缀
QString suffix() const
void setSuffix(const QString &suffix)
```
# 相关