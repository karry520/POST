---
title: Shell-Part3-/etc/profile
tags: Shell
date: 2018-02-01 10:00:13
---
登录系统时，在进入命令提示符前，系统要做两个工作。键入用户名和密码后，系统检查是否为有效用户，为此需查询/etc/passwd文件。如果登录名正确并且密码有效，开始下一步过程，即登录环境。
- ### /etc/profile

---
用户登录时，自动读取/etc目录下profile文件，此文件包含：
~~~
    • 全局或局部环境变量。
    • PATH信息。
    • 终端设置。
    • 安全命令。
    • 日期信息或放弃操作信息。
~~~
- ### 用户的$HOME.profile

---
/etc/profile文件执行时，用户将被放入到自己的$HOME目录中，回过头来观察passwd文件，用户的$HOME目录在倒数第2列。可以将之看作用户根目录，因为正是在这里存储了所有的私有信息。如果.profile已经存在，系统将参照此文件，意即对此过程并不创建另一个shell，因而在/etc/profile下设置的环境不做改动，除非在.profile中强制改动它。如果创建另一个进程，用户本地的shell变量将被覆盖。回到.profile，一般来说创建帐户时，一个profile文件的基本框架即随之创建。不要忘了在.profile文件中可以通过设置相关条目以不同的值或使用uset命令来覆盖/etc/profile文件中的设置。如果愿意，可以定制用户自己的.profile文件。

~~~
$cat /etc/profile
~~~
- ### stty用法

---
stty用于设置终端特性。
~~~
$stty -a 
~~~
- ### 创建.logout文件

---
使用Bourne shell与其他shell不同，其缺点是不包含.logout文件。此文件保存有执行exit命令时，在进程终止前执行的命令。
~~~
#配置.profile
$stty erase '\^H'
~~~
