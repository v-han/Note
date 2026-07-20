---
updated: 2026-07-20 20:48
created: 2026-07-20 20:22
tags:
---
# 介绍
[[git log命令]]的选项，使输出格式化。
# 使用方式
使用`--pretty`接上输出的格式。
```bash
git log --pretty=oneline
```
# 选项
下面是`--pretty`的一些常见子选项。

| 子选项                   | 功能      |
| --------------------- | ------- |
| oneline               | 使输出在一行。 |
| short                 | 简短的输出。  |
| full                  | 详细输出。   |
| fuller                | 更详细输出。  |
| [[format子选项\|format]] | 定制显示格式。 |

# 相关