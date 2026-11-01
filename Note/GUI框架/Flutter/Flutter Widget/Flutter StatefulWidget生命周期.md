---
updated: 2026-10-26 16:36
created: 2026-10-26 14:21
tags:
---
# 介绍
**有状态组件**通过`createState`创建关联的**State**对象，其**生命周期**主要由**State**管理。
# 使用方式
通过构造函数创建**Widget**，并通过`createState`创建关联的**State**对象。

**State**对象首先执行`initState`方法初始化，然后执行`didChangeDependencies`方法处理依赖关系，最后执行`build`方法构建用户界面。

> [!NOTE]
> `didChangeDependencies`还会在所依赖的[[Flutter InheritedWidget|InheritedWidget]]更新且通知其子孙组件更新时被调用并执行`build`构建用户界面。

当**State**中的状态发生变化并调用`setState`时，**Flutter**会重新调用`build`方法构建界面。或当父组件更新当前**Widget**的配置且原**State**被复用时，**Flutter**会调用`didUpdateWidget`方法，然后重新调用`build`方法。

> [!NOTE]
> `didUpdateWidget`方法在父组件使用新的Widget配置更新当前组件被调用，`didChangeDependencies`在初始化和依赖更新时被调用。

当组件从**Widget树**中移除时，会调用`deactivate`方法，如果组件被永久移除，则调用`dispose`方法释放资源。
# 相关