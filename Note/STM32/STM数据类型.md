---
updated: 2026-09-13 15:54
created: 2026-07-31 21:19
tags:
---
# 介绍
由于不同平台的数据类型大小不一样，使用<stdint.h>头文件中的数据类型提高精确性和可移植性。
# 使用方式
引入头文件。
```C
#include <stdint.h>
```

使用变量时以以下的数据类型定义。

| 原关键字                   | 位数  | stdint关键字    | ST关键字 |
| ---------------------- | --- | ------------ | ----- |
| **char**               | 8   | **int8_t**   | s8    |
| **unsigned char**      | 8   | **uint8_t**  | u8    |
| **short**              | 16  | **int16_t**  | s16   |
| **unsigned short**     | 16  | **uint16_t** | u16   |
| **int**                | 32  | **int32_t**  | s32   |
| **unsigned int**       | 32  | **uint32_t** | u32   |
| **long**               | 32  |              |       |
| **unsigned long**      | 32  |              |       |
| **long long**          | 64  | **int64_t**  |       |
| **unsigned long long** | 64  | **uint64_t** |       |
# 相关