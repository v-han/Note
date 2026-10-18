---
updated: 2026-10-15 23:06
created: 2026-10-14 21:35
tags:
---
# 介绍
**TS**的代码需要通过编译成**JS**代码才能在**JS**的运行环境中运行。
# 使用方式
为**Node.js**安装**typescript**。
```bash
npm install -g typescript
```

使用`tsc`可将**TS**代码编译为**JS**代码。
```bash
tsc main.ts
```

使用`tsx`可直接调试**TS**代码(内部仍是先转换为**JS**再运行)。
```bash
# 需要安装 tsx 包
npm install -g tsx
tsx main.ts
```
# 相关