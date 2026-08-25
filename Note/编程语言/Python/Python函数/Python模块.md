---
updated: 2026-08-22 17:03
created: 2026-08-22 13:24
tags:
---
# 介绍
**Python模块**(module)是Python程序的基本组织单位。一个`.py`文件就是一个**模块**，**Python**提供了一些标准**模块**，除此之外还可以自定义**模块**。
在**模块**中可以定义变量、函数、类和可执行代码。
# 使用方式
使用`import`导入模块，一般导入模块的代码都是放在文件的开头。
```python
import random

# 此时使用模块内的函数要使用 . 的方式。
num_rand = random.randint(1, 100)
```

使用`from`和`import`能够导入模块中的指定功能，导入多个功能时用`,`分隔，可以使用`*`导入模块的所有功能。
```python
from random import randint

# 此时可以直接用指定的函数，未导入的无法使用。
num_rand = randint(1, 100)
```

使用`as`为导入的模块或功能起别名。有的模块或功能可能名字比较长，以这种方式能够方便调用。
```python
import random as rd

from random import randint as rdint
```

> [!NOTE]
> 使用**模块**开发能够提高代码复用性、降低开发门槛。
# 相关
[[Python自定义模块]]
[[Python软件包]]