---
updated: 2026-07-21 22:40
created: 2026-07-20 21:56
tags:
---
# 介绍
使用Git分支可以将开发工作和从开发主线中分离开来，避免影响主线开发。
Git分支实际上是指向[[Git提交|提交对象]]的可变指针。
为了指出当前分支，Git使用一个`HEAD`的指针指向**当前所在的本地分支**。
# 使用方式
使用[[git branch命令]]创建一个分支。
```bash
git branch develop
```

这样就创建一个`develop`的分支，这个命令只创建分支不跳转。

> [!NOTE]
> 当使用`git init`时就会自动创建`master`分支。

使用[[git checkout命令]]来切换分支。
```bash
git checkout develop
```

这样就切换回`develop`分支。
# 相关
对于一个**提交对象**的两个分支都产生了提交，就会发生[[项目分叉]]现象。