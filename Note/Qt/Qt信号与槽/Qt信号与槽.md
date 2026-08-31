---
updated: 2026-08-28 18:28
created: 2026-08-24 19:51
tags:
---
# 介绍
**信号**(Signal)：当某个实例化对象发生事件时，就会发出信号。
**槽**(Slot)：即槽函数，用于实现特定功能。
# 使用方式
使用`connect()`方法来连接**信号**与**槽**。该方法有多个重载，但都是按以下的格式。
```cpp
connect(sender, signal, receiver, slot)
// sender: 发送信号的对象。
// signal: 发送的信号。
// receiver: 接收信号的对象。
// slot: 接收信号后执行的方法，即槽函数。
```

在**Widget**的构造函数里进行**信号槽**的关联(这里用函数地址的方式，Qt4的`SIGNAL`和`SLOT`宏的方式略过)。
```cpp
# 将 btnMax 按钮绑定 QWidget 的最大展示方法。
connect(ui->btnMax, &QPushButton::clicked, this, &QWidget::showMaximized);
```

使用`emit`关键字发射**信号**。
```cpp
emit classTest->testSignal()

// emit 关键字可以省略。
classTest->testSignal()
```

在ui设计界面可以图形化编辑**信号与槽**，这种方式是直接写到ui文件中，通过[[UIC]]转换为可编译的文件。

> [!NOTE]
> 一个**信号**能够连接多个**槽**，在信号发射后这些**槽函数**的执行顺序与建立连接的顺序相同(在Qt5之后)。一个**槽**也能连接多个**信号**。**信号**也能连接**信号**，发送信号后触发接收信号的对象发射信号。
> 
> **信号与槽**连接的参数和返回值[[信号与槽的连接规则|规则]]。

使用`disconnect()`断开连接。在一个对象被`delete`了之后，Qt会自动断开连接到这个对象的所有槽。
```cpp
// 断开所有连接到 classTest 信号上的槽函数。
classTest->disconnect();
```
# 相关
在槽函数里可以使用[[Qt lambda|lambda表达式]]。
[[信号与槽重载]]
[[自定义信号与槽]]
