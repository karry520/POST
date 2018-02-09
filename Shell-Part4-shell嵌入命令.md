---
title: Shell-Part4-shell嵌入命令
tags: Shell
date: 2018-02-01 10:02:20
---
- ### 标准嵌入命令

---
~~~
：          空，永远返回为true
.           从当前shell中执行操作
break       退出for、while、until或case语句
cd          改变到当前目录
continue    执行循环的下一步
echo        反馈信息到标准输出
eval        读取参数，执行结果命令
exec        执行命令，但不在当前shell   
exit        退出当前shell
export      导出变量，使当前shell可利用它
pwd         显示当前目录
read        从标准输入读取一行文本
readonly    使变量只读
return      退出函数并带有返回值
set         控制各种参数到标准输出的显示
shift       命令行参数向左偏移一个
test        评估条件表达式
times       显示shell运行过程的用户和系统时间
trap        当捕获信号时运行指定命令
ulimit      显示或设置shell资源
umask       显示或设置缺省文件创建模式
unset       从shell内存中删除变量或函数
wait        等待直到子进程运行完毕，报告终止
~~~


