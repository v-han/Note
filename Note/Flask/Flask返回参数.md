---
updated: 2026-07-08 20:54
created: 2026-07-08 20:49
tags:
---
# 介绍
在一般的Web开发中，返回数据基本是用JSON格式的，从而方便开发者调用。
Flask框架提供了一种将字典转换为JSON的方法。
# 开发步骤
使用jsonify方法将字典转换为JSON格式数据。
```Python
# 导入对应的软件包(jsonify)
from flask import Flask, jsonify

# 略过其他代码
@app.route("/index")
def index():
	return jsonify({"status": True, "data": "data"})
```
# 相关