---
updated: 2026-09-16 15:58
created: 2026-09-16 13:45
tags:
---
# 介绍
**CMake**的函数，分别为**宏**(Marco)和**函数**(Function)。和**C**语言一样，前者只是文本地替换，后者才是真正意义的函数。
# 使用方式
使用`macro()`和`function()`分别定义宏和函数。
```cmake
# 表示创建一个 MarcoAppend 的宏，后面的是参数。
macro(MacroAppend ListVar Value)
  # 使用 ${ListVar} 表示获取 ListVar 传进来的参数
  # ${${ListVar}} 表示获得列表的值
  set(${ListVar} "${${ListVar}};${Value}")
endmacro()

# 表示创建一个 FuncAppend 的函数，后面的是参数。
function(FuncAppend ListVar Value)
  MacroAppend(${ListVar} ${Value})
  # 使用 PARENT_SCOPE 表示将结果写回到父作用域，即返回。
  set(${ListVar} "${${ListVar}}" PARENT_SCOPE)
endfunction()
```

在使用宏或者函数时，除给定的参数列表，多接收的参数都在`ARGN`中。
```cmake
function(FilterFoo OutVar)
  # 使用 ARGN 接收多余的参数
  foreach(item IN LISTS ARGN)
    if(item MATCHES Foo)
      list(APPEND ${OutVar} ${item})
    endif()
  endforeach()
  set(${OutVar} ${${OutVar}} PARENT_SCOPE)
endfunction()
```
# 相关