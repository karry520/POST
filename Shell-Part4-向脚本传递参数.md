---
title: Shell-Part4-向脚本传递参数
tags: Shell
date: 2018-02-01 10:01:28
---
前面已经讲到如何使用特定变量$1..$9向脚本传递参数。$#用于统计传递参数的个数。可以创建一个usage语句，需要时可通知用户怎样以适当的调用参数调用脚本或函数。
- ### shift命令

---
向脚本传递参数时，有时需要将每一个参数偏移以处理选项，这就是shift命令的功能。它每次将参数位置向左偏移一位，下面用一段简单脚本详述其功能。脚本使用while循环反馈所有传递到脚本的参数。
~~~
#!/bin/sh
loop=0
while [ $# -ne 0 ]
do 
    echo $1
    shift       #偏移到下一个参数　
done
~~~
- ### getopts　

---
getopts可以编写脚本，使控制多个命令行参数更加容易。getopts用于形成命令行处理标准形式。原则上讲，脚本应具有确认带有多个选项的命令文件标准格式的能力。
~~~
#getopts一般格式为:
getopts option_string variables
#option_string为(-a,-h-f,-v,-g)
~~~
