---
updated: 2026-07-08 20:48
created: 2026-07-08 18:42
tags:
---
# 开发步骤
使用前需要导入Flask框架。
```Python
from flask import Flask
```

创建Flask实例。
```Python
app = Flask(__name__)
```

编写[[Flask控制层？|路由映射方法]]。
```Python
@app.route("/index")
def index():
	return "seccess"
```

这里路由和函数名最好保持一致，方便后续的维护。
运行app实例。
```Python
if __name__ == '__main__':
	app.run()
```

> [!NOTE]
> 可以再`app.run()`中添加`host`和`port`来指定端口号。
# 相关