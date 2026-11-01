---
updated: 2026-10-26 21:21
created: 2026-10-23 20:01
tags:
---
# 介绍
**Flutter**中的**Widget**是中构建用户界面的基本单位，用于描述界面元素的**配置**、**外观**和**布局**。
# 使用方式
**Widget**具有以下的特点：
1. **组合性**：多个**Widget**可以组合起来构建复杂的用户界面。
2. **不可变性**：**Widget**本身是不可变的，创建后**不能直接**修改其属性。
3. **响应式**：当状态发生变化时，会重新创建**Widget**更新界面。

**Flutter**的**Widget**分为[[Flutter StatelessWidget|无状态组件]]和[[Flutter StatefulWidget|有状态组件]]，**Flutter**通过嵌套**Widget**构建界面，这些**Widget**形成的层次结构称为**Widget树**。
# 相关
[[Flutter InheritedWidget]]
[[Flutter Event]]
[[Flutter容器与布局组件]]