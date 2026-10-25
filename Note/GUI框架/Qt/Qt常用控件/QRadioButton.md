---
updated: 2026-09-06 17:30
created: 2026-09-04 23:37
tags:
---
# 介绍
**QRadioButton**是**Qt**中用于单选操作的类。继承自[[QAbstractButton]]。
# 使用方式
使用`isChecked()`和`setChecked()`控制按钮的选中状态。
```cpp
// 获取按钮的选中状态
bool isChecked() const
// 设置按钮的选中状态
void setChecked(bool)
```

使用`autoExclusive()`和`setAutoExclusive()`控制按钮的排他性(默认是`ture`，即排他)。
```cpp
// 获取按钮的排他属性
bool autoExclusive() const
// 设置按钮的排他属性
void setAutoExclusive(bool)
```

> [!NOTE]
> 使用排他功能时，应该将按钮放在一个`Widget`或`GroupBox`中，使按钮与指定的按钮进行多选一的操作。
> 或者在代码中使用`QButtonGroup`将一组按钮使用`addButton()`添加到对应的按钮组中。
# 相关