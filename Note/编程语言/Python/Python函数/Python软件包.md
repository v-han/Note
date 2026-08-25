---
updated: 2026-08-22 18:51
created: 2026-08-22 17:03
tags:
---
# 介绍
**Python软件包**(package)本质就是一个文件夹，用于管理多个模块。
这个文件夹中包含多个**Python模块**，文件夹下还包含一个`__init__.py`。
# 使用方式
在导入模块时还需要多一层软件包名，其他和**模块**的导入差不多。
```python
import utils.my_funs

# 从包中带入模块。
from utils import my_funs

# 从包中的模块中导入功能。
from utils.my_funs import my_add
```

使用`__all__`来配置`from 软件包 import *`时通配的模块。
```python
__all__ = ["my_funs", "my_class"]
```
# 相关