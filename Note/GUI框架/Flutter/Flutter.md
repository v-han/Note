---
updated: 2026-10-23 18:01
created: 2026-10-23 01:24
tags:
---
# 介绍
**Flutter**是由Google主导开发的开源跨平台应用程序**UI框架**，使用[[Dart]]编程语言。
这部分笔记来自[黑马程序员](https://www.bilibili.com/video/BV1wR4Xz6EqG/?spm_id_from=333.788.videopod.episodes&vd_source=caedb35a1b601f1d5184d2b7fbb4c8ec&p=38)。
# 使用方式
使用`create`来创建**Flutter**项目，一般项目由**小写字母**、**数字**和**下划线**组成且符合**命名规范**。
```bash
flutter create <项目名称>
// 可以使用 platforms 参数来指定构建平台，多个平台用 , 分开
flutter create --platforms <构建平台> <项目名称>
```

在**Flutter**项目中，`lib`目录用于存放[[Flutter代码编写|源代码]]，各平台对应的目录(如 `android`、`web`)用于存放平台相关的配置和原生代码，`pubspec.yaml`文件用于管理**项目配置**、**依赖信息**及**资源文件**。

# 相关
[Flutter文档](https://docs.flutterdart.cn/)(包含下载安装方式)。