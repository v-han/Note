---
updated: 2026-10-15 15:30
created: 2026-07-05 21:00
tags:
---
# 介绍
Git的配置文件存放在`~etc/gitconfig`和`C:/Users/$USER/.gitconfig`里。可以使用`git config`命令查看配置信息。
# 初次运行前的配置
在安装完Git之后，要配置用户名和邮箱地址，之后的每一次提交都会带上这个信息。
```bash
git config --global user.name "yourname"
git config --global user.email youremail@example.com
```

> [!NOTE] 
> 如果在某些项目中需要使用不同的由用户名或邮箱地址时，可以运行不带`--global`选项的命令来配置。
# 可选配置
可以为Git配置文本编辑器。
```bash
git config --global core.editor <文本编辑器>
```
# 查看配置
可以使用`git config --list`命令来查看配置。
```bash
git config --list
```

可以加上`--show-origin`选项查看配置所在的文件。
```bash
git config --list --show-origin
```
# 相关