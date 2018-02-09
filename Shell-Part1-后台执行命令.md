---
title: Shell-Part1-后台执行命令
tags: Shell
date: 2018-02-01 09:58:10
---
当你在终端或控制台工作时，可能不希望由于运行一个作业而占住了屏幕，因为可能还有更重要的事情要做，比如阅读电子邮件。对于密集访问磁盘的进程，你可能希望它能够在每天的非负荷高峰时间段运行。为了使这些进程能够在后台运行，也就是说不在终端屏幕上运行，有几种选择方法可供使用。

    • 设置crontab文件，并用它来提交作业。
    • 使用at命令来提交作业。
    • 在后台提交作业。
    • 使用nohup命令提交作业。

- ### cron和crontab 

---
cron是系统主要的调度进程，可以在无需人工干预的情况下运行作业。有一个叫做crontab的命令允许用户提交、编辑或删除相应的作业。每一个用户都可以有一个crontab文件来保存调度信息。可以使用它运行任意一个shell脚本或某个命令，每小时运行一次，或一周三次，这完全取决于你。每一个用户都可以有自己的crontab文件，但在一个较大的系统中，系统管理员一般会禁止这些文件，而只在整个系统保留一个这样的文件。系统管理员是通过cron.deny和cron.allow这两个文件来禁止或允许用户拥有自己的crontab文件。
- #### crontab格式

~~~
#crontab格式
分<>时<>时<>月<>星期<>要运行的命令
~~~
例程：
~~~
30 21* * * /apps/bin/cleanup.sh
#表示每天21:30运行/apps/bin/目录下的cleanup.sh
~~~
- #### crontab命令选项

crontab命令的一般形式为：
~~~
$crontab [-u user] -s -l -r
    -u  用户名
    -e  编辑crontab文件
    -l  列出crontab文件中的内容
    -r  删除crontab文件   
~~~
~~~
#创建一个新的crontab文件
#设置编辑器
$EDITOR=vim; export EDITOR
#创建一个crontab文件,如karrycron
$crontab karrycron
~~~
- ### at命令

---
at命令允许用户向cron守护进程提交作业，使其在稍后的时间运行。这里稍后的时间可能是指10min以后，也可能是指几天以后。如果你希望在一个月或更长的时间以后运行，最好还是使用crontab文件。
~~~
$at [-f script] [-m -l -r] [time] [date]
其中，
-f       script是所要提交的脚本或命令。
-l       列出当前所有等待运行的作业。atq命令具有相同的作用。
-r       清除作业。为了清除某个作业，还要提供相应的作业标识（ID）；有些UNIX变体只接受atrm作为清除命令。
-m       作业完成后给用户发邮件。
time     at命令的时间格式非常灵活；可以是H、HH . HHMM、HH:MM或H:M，其中H和M分别是小时和分钟。还可以使用a.m.或p.m.。
date     日期格式可以是月份数或日期数，而且at命令还能够识别诸如today、tomorrow这样的词。
~~~
例程：
~~~
#命令行方式　
$at 3.00pm tomorrow -f /apps/bin/db table.sh
$echo find /etc -name "passwd" -print | at now +1 minute
#交互式
$at 21:10
at>find / -name "passwd" -print
at><EOT> 
#<EOT>就是<CTR-D>
~~~
- ### &命令

---
当在前台运行某个作业时，终端被该作业占据；而在后台运行作业时，它不会占据终端。可以使用&命令把作业放到后台执行。
例程：
~~~
$command > out.file 2>&1 &
#查看进程　
$ps [-ef -x] | grep 进程号  
~~~
- ### nohup命令

---
如果你正在运行一个进程，而且你觉得在退出帐户时该进程还不会结束，那么可以使用nohup命令。该命令可以在你退出帐户之后继续运行相应的进程。Nohup就是不挂起的意思(nohang up)。如果使用nohup命令提交作业，那么在缺省情况下该作业的所有输出都被重定向到一个名为nohup.out的文件中，除非另外指定了输出文件
例程：
~~~
$nohup command > myout.file 2>&1 &
~~~
