---
title: Shell-Part4-调试脚本
tags: Shell
date: 2018-02-01 10:02:12
---
shell编程最烦人的一项工作是调试问题。有一些方法可以借鉴，但是最好能在问题出现前防止大部分错误，为此应遵循以下规则。将设计脚本分成几个任务或过程，然后在继续下一步前分别予以测试。
- ### 一般错误　

---
循环错误
~~~
syntax error near unexpected token 'done'
line xx:'done'
~~~
典型的漏写引号
~~~
unexpected EOF while looking for '"'
line xx:syntax error 
~~~
测试错误　
~~~
[: missing ']'
~~~
字符大小写
~~~
多发生在变量使用时
~~~
for循环
~~~
在循环的列表部分用$符号，特别是在读取字符串时
~~~
echo
~~~
不要在echo 后面使用最后状态命令，因为恒true
~~~
- ### set命令

---
set命令可辅助脚本调试。以下是set命令常用的调试选项：
~~~
set -n   读命令但并不执行。
set -v   显示读取的所有行。
set -x   显示所有命令及其参数。
~~~

