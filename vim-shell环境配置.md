---
title: vim-shell环境配置
tags: Vim
date: 2018-02-02 18:25:09
---
- ### 什么是bash-support.vim插件

---
Bash-support是一个高度定制化的vim插件，使得bash脚本编程变得有趣和愉快。
- ### 安装

---
~~~
$vim .vimrc
    add "Plugin 'WolfganMehner/bash-support'"
$vim 
    :BundleInstall   
~~~
- ### 常用快捷键

---
下面是一些用于插入语句的键映射（n – 普通模式, i – 插入模式，v 可视模式）：
~~~
    \sc  – case in … esac （n, i）
    \sei – elif then （n, i）
    \sf  – for in do done （n, i, v）
    \sfo – for ((…)) do done （n, i, v）
    \si  – if then fi （n, i, v）
    \sie – if then else fi （n, i, v）
    \ss  – select in do done （n, i, v）
    \su  – until do done （n, i, v）
    \sw  – while do done （n, i, v）
    \sfu – function （n, i, v）
    \se  – echo -e "…" （n, i, v）
    \sp  – printf "…" （n, i, v）
    \sa  – 数组元素, ${.[.]} （n, i, v） 和其它更多的数组功能。
~~~

- ### 运行操作

---
~~~

    \rr  – 更新文件，运行脚本（n, i）
    \ra  – 设置脚本命令行参数 （n, i）
    \rc  – 更新文件，检查语法 （n, i）
    \rco – 语法检查选项 （n, i）
    \rd  – 启动调试器（n, i）
    \re  – 使脚本可/不可执行(*) （n, i）

~~~


