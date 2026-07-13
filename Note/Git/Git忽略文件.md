---
updated: 2026-07-06 16:26
created: 2026-07-06 02:43
tags:
---
# 介绍
在Git仓库目录下编写一个`.gitignore`文件来列出要忽略的文件。
# 编写格式
以#开头的行和空行都会被Git忽略。
```.gitignore
# 可以用这种方式写注释。
```

使用标准的[[glob模式]]匹配，这会递归的应用在整个工作区。
```.gitignore
# 忽略所有.c文件。
*.c
```

使用`/`开头防止递归。
```.gitignore
# 忽略当前目录下的该名字文件或目录，不忽略其他目录下的同名文件或目录。
/filename
```

使用`/`结尾指定目录。
```.gitignore
# 忽略任何目录下的build目录。
build/
```

使用`!`来跟踪前面忽略的文件。
```.gitignore
*.c


# 前面已经忽略了.c文件，但是仍然跟踪1.c文件。
!1.c
```

> [!NOTE]
> 在仓库根目录的`.gitignore`文件应用在整个Git仓库，也可以在子目录中创建`.gitignore`文件在只在子目录中生效。
# 相关
GitHub还有其他的针对不同语言的`.gitignore`文件列表，可以在[这里](https://github.com/github/gitignore)。
更多的`.gitignore`文件细节使用`man gitignore`查看。