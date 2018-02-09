---
title: Shell-Part5-几个脚本例子
tags: Shell
date: 2018-02-01 10:03:10
---
- ### 简单例子

---
~~~
#!/bin/bash -
#===============================================================================
#
#          FILE: shell-script.sh
#
#         USAGE: ./shell-script.sh
#
#   DESCRIPTION: 
#
#       OPTIONS: ---
#  REQUIREMENTS: ---
#          BUGS: ---
#         NOTES: ---
#        AUTHOR: KARRY (), 884816926@qq.com
#  ORGANIZATION: USC
#       CREATED: 2018年02月09日 10时53分56秒
#      REVISION:  ---
#===============================================================================

set -o nounset                                  # Treat unset variables as an error


#-------------------------------------------------------------------------------
# first.sh
#-------------------------------------------------------------------------------
echo "Hello      World"       # This is a comment, too!
echo "Hello World"
echo "Hello * World"
echo  Hello * World
echo  Hello      World
echo "Hello" World
echo  Hello "     " World
echo "Hello "*" World"
echo `hello` world
echo 'hello' world

#-------------------------------------------------------------------------------
# Variables.sh
#-------------------------------------------------------------------------------
echo -e "What is your name?"
read USER_NAME

echo -e "Hello $USER_NAME"
echo -e "I will create you a file called ${USER_NAME}_file"
touch ${USER_NAME}_file
rm ${USER_NAME}_file

#-------------------------------------------------------------------------------
# Loops.sh
#-------------------------------------------------------------------------------
#for loops

for i  in 1 2 3 4 5; do
    echo -e "Looping ... number $i"
done


for i in hello 1 * 2 goodbye; do
    echo -e "Looping ... i is set to $i"
done


for runlevel in 0 1 2 3 4 5 5 S; do
    mkdir rc${runlevel}.d
    rm -d rc${runlevel}.d
done
#while loops
INPUT_STRING=hello
while [ "$INPUT_STRING" != "bye" ] ; do
    echo -e "Please type something in (bye to quit)"
    read INPUT_STRING
    echo "You typed: $INPUT_STRING"
done


while read f; do

    case $f in
        hello)
            echo -e "English"
            ;;

        howdy)
            echo -e "American"
            ;;

        *)
            echo -e "Unknown Language:$f"
            ;;

        esac    # --- end of case ---
done < myfile


#-------------------------------------------------------------------------------
# test.sh
#-------------------------------------------------------------------------------
read X
if [ "$X" -lt "0" ] ; then
    echo -e "X is less than zero"
else
    echo -e "X is better or equal zero "
fi


#-------------------------------------------------------------------------------
# Variables2.sh
#-------------------------------------------------------------------------------
#IFS是系统设定的分割符
old_IFS="$IFS"
IFS=:
echo -e "Please input some data separated by colons ..."
read x y z 
IFS=$old_IFS
echo -e "x is $x y is $y z is $z"


#-------------------------------------------------------------------------------
# Variables3.sh
#-------------------------------------------------------------------------------
echo -en "What is your name [ `whoami`  ]"
read myname 

if [ -z "$myname" ] ; then
    myname=`whoami`
fi
echo -e "Your name is : $myname"


#-------------------------------------------------------------------------------
# function.sh
#-------------------------------------------------------------------------------

myfunc ()
{
    echo -e "I was called as : $@"
    x=2
}	# ----------  end of function myfunc  ----------

echo -e "Script was called with $@"
x=1
echo -e "x is $x"
myfunc 1 2 3 
echo -e "x is $x"


#-------------------------------------------------------------------------------
# exersic 
#-------------------------------------------------------------------------------

doindent ()
{
    j=0;
    
    while [ "$j" -lt "$1" ] ; do
        echo -en "  "
        j=`expr $j + 1`
    done
}	# ----------  end of function doindent  ----------


traverse ()
{
    cd "$1"
    ls | while read i ; do
        doindent $2
        if [ -d "$i" ] ; then
            echo -e "Directory: $i"
            (traverse "$i" `expr $2 + 1`)
        else 
            echo -e "File : $i"
        fi
    done
}	# ----------  end of function traverse  ----------


if [ -z "$1" ] ; then
    traverse . 0
else
    traverse "$1" 0
fi
~~~
- ###

---

