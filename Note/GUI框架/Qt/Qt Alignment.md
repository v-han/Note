---
updated: 2026-08-30 12:12
created: 2026-08-30 11:02
tags:
---
# 介绍
**Qt**中用于设置对其方式的**枚举类**。
# 使用方式
`Qt::Alignment`常用的取值如下。

| 枚举                                                   | 值      | 含义             |
| ---------------------------------------------------- | ------ | -------------- |
| Qt::AlignLeft                                        | 0x0001 | 水平方向-左对齐       |
| Qt::AlignRight                                       | 0x0002 | 水平方向-右对齐       |
| Qt::AlignHCenter                                     | 0x0004 | 水平方向-居中对齐      |
| Qt::AlignTop                                         | 0x0020 | 垂直方向-上对齐       |
| Qt::AlignBottom                                      | 0x0040 | 垂直方向-下对齐       |
| Qt::AlignVCenter                                     | 0x0080 | 垂直方向-居中对齐      |
| Qt::AlignCenter<br>(AlignVCenter \|<br>AlignHCenter） | 0x0084 | 垂直方向和水平方向-居中对齐 |

> [!NOTE]
> 上面的枚举都是16进制的一位，可以使用`|`来设置多种方式。
# 相关