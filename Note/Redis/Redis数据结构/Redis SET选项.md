---
updated: 2026-09-18 18:23
created: 2026-09-18 17:39
tags:
---
# 介绍
**Redis**的`SET`命令的选项。
# 使用方式
完整的`SET`命令是这样的。这里本该是一行，这里按选项进行分类换行。
```redis
SET key value 

[NX | XX | IFEQ ifeq-value | IFNE ifne-value |  IFDEQ ifdeq-digest | IFDNE ifdne-digest] 

[GET] 

[EX seconds |  PX milliseconds | EXAT unix-time-seconds |  PXAT unix-time-milliseconds | KEEPTTL]
```

**第一个可选部分**：
1. `NX`：仅当此**key**不存在时为其**value**赋值。
2. `XX`：仅当此**key**存在时为其**value**赋值。
3. `IFEQ`：仅当此**key**的**value**等于`ifeq-value`为其**value**赋值(当**key**不存在时也不会赋值)。
4. `IFNE`：仅当此**key**的**value**不等于`ifne-value`为其**value**赋值(当**key**不存在时会赋值)。
5. `IFDEQ`
6. `IFDNE `

**第二个可选部分**：
`GET`：返回此**key**原来的**value**，若此**key**原来不存在也返回**nil**。

**第三个可选部分**：
1. `EX`：设置此**key**的有效期，单位是**秒**。
2. `PX`：设置此**key**的有效期，单位是**毫秒**。
3. `EXAT`：设置此**key**的有效期，使用**Unix时间戳**(秒)的方式。
4. `PXAT`：设置此**key**的有效期，使用**Unix时间戳**(毫秒)的方式。

# 相关