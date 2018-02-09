---
title: Shell-Part2-AWK介绍
tags: Shell
date: 2018-02-01 09:59:26
---
如果要格式化报文或从一个大的文本文件中抽取数据包，那么awk可以完成这些任务。它在文本浏览和数据的熟练使用上性能优异。
- ### 调用awk

---
有三种方式调用awk:
~~~
awk [-F field-separator] 'commands' input-file(s)

awk -F:'commands' input-file
~~~
第二种方法是将所有awk命令插入一个文件，并使awk程序可执行，然后用awk命令解释器作为脚本的首行，以便通过键入脚本名称来调用它。
第三种方式是将所有的awk命令插入一个单独文件，然后调用：
~~~
awk -f awk-script-file input-files(s)
~~~
- ### awk脚本

---
在命令中调用awk时，awk脚本由各种操作和模式组成。
~~~

~~~
