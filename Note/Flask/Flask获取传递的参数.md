---
updated: 2026-07-08 20:41
created: 2026-07-08 20:40
tags:
---
# 介绍
从请求中获取传递的参数。
# 开发步骤
如果需要得到传递的参数。
```Python
# 导入需要的软件包(request)
from flask import Flask, request

# 其他代码略
@app.route("/index")
def index():
	age = request.args.get("age")
	pwd = request.args.get("pwd")
	return "success"
```

默认情况下，`@app.route()`方法只接受**GET**请求，如果需要接收其他请求需要为`methods`传参。
```Python
@app.route("/index", methods="POST")
@app.route("/index", methods=["POST", "GET"])
```

> [!NOTE]
> 当使用请求体发送请求时，获取传递参数的方法要修改为`request.form.get()`。
> 当使用JSON格式发送请求时，获取传递参数的方法要修改为`request.json.get()`。
# 相关