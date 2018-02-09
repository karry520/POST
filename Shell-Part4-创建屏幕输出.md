---
title: Shell-Part4-创建屏幕输出
tags: Shell
date: 2018-02-01 10:01:39
---
用户可以使用shell脚本创建交互性的、专业性强的屏幕输出。要实现这一点，系统上需要一个彩色监视器和tput命令。
- ### tput

---
在使用tput前，需要在脚本或命令行中使用tput命令初始化终端。
~~~
$tput init
~~~
tput产生三种不同的输出：字符型、数字型和布尔型（真/假）。以下分别介绍其使用功能。
- ### tput用法　

---
~~~
#!/bin/bash
printf $(tput setaf 2; tput bold)'color show\n\n'$(tput sgr0)

for((i=0; i<=7; i++)); do
    echo $(tput setaf $i)"show me the money"$(tput sgr0)
done

printf '\n'$(tput setaf 2; tput setab 0; tput bold)'background color show'$(tput sgr0)'\n\n'

for((i=0,j=7; i<=7; i++,j--)); do
    echo $(tput setaf $i; tput setab $j; tput bold)"show me the money"$(tput sgr0)
done

exit 0

#输出格式控制函数:
#!/bin/bash

# $1 str       print string
# $2 color     0-7 设置颜色
# $3 bgcolor   0-7 设置背景颜色
# $4 bold      0-1 设置粗体
# $5 underline 0-1 设置下划线

function format_output(){
    str=$1
    color=$2
    bgcolor=$3
    bold=$4
    underline=$5
    normal=$(tput sgr0)

    case "$color" in
        0|1|2|3|4|5|6|7)
            setcolor=$(tput setaf $color;) ;;
        *)
            setcolor="" ;;
    esac

    case "$bgcolor" in
        0|1|2|3|4|5|6|7)
            setbgcolor=$(tput setab $bgcolor;) ;;
        *)
            setbgcolor="" ;;
    esac

    if [ "$bold" = "1" ]; then
        setbold=$(tput bold;)
    else
        setbold=""
    fi

    if [ "$underline" = "1" ]; then
        setunderline=$(tput smul;)
    else
        setunderline=""
    fi

    printf "$setcolor$setbgcolor$setbold$setunderline$str$normal\n"
}

format_output "Yesterday Once more" 2 5 1 1

exit 0
~~~
