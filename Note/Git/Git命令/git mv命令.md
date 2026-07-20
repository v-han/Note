---
updated: 2026-07-20 20:24
created: 2026-07-06 23:26
tags:
---
# 介绍
使用该命令对文件进行移动。
Git不会显示跟踪文件的移动操作，而是自己推导。
和Linux里一样，使用`mv`命令可以对文件进行改名。
# 使用方式
使用`git mv`命令移动文件或者重命名。
```bash
git mv <文件地址或名字> <文件新地址或名字>
```

其实等价于运行下面三条命令。
```bash
mv file1 file2
git rm file1
git add file2
```
# 相关