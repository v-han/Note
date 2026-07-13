---
updated: 2026-07-06 01:30
created: 2026-07-06 00:57
tags:
---
# 介绍
有两种方式能够建立Git仓库。
1. 在没有版本控制的本地目录下建立Git仓库。
2. 从其他服务器中**克隆**一个已经存在的Git仓库。
# 建立Git仓库
在要进行版本控制的目录下打开Shell或打开Shell后转到对应的目录下。使用`git init`命令创建一个Git仓库。
```bash
git init
```

在对应的目录下会出现一个`.git`目录，存放Git仓库的必须文件。
# 克隆仓库
在Shell中使用`git clone`命令，克隆一个已存在的Git仓库。
```bash
git clone <url>
```

这样会在当前目录下创建一个该Git仓库的目录。
可以通过额外的参数来改变仓库的目录名。
```bash
git clone <url> name
```

这样就会在当前目录下创建指定目录名的Git目录。
# 相关