---
title: Shell-Part4-条件测试
tags: Shell
date: 2018-02-01 10:00:59
---
写脚本时，有时要判断字符串是否相等，可能还要检查文件状态或是数字测试。基于这些测试才能做进一步动作。Test命令用于测试字符串，文件状态和数字，也很适合于下一章将提到的if、then、else条件结构
- ### 测试文件状态

---
test一般有两种格式，即：
~~~
test condition
或
[condition]

-d     目录
-s     文件长度大于0、非空
-f     正规文件
-w     可写
-L     符号连接
-u     文件有suid位设置
-r     可读
-x     可执行
~~~
~~~
$test -w file
$echo $?
~~~
- ### 测试时使用逻辑操作符

---
测试文件状态是否为OK，但是有时要比较两个文件状态。shell提供三种逻辑操作完成此功能。
~~~
-a   逻辑与，操作符两边均为真，结果为真，否则为假。
-o   逻辑或，操作符两边一边为真，结果为真，否则为假。
!    逻辑否，条件为假，结果为真。
~~~
~~~
$[ -w file1 -a -r file2 ]
$echo $?
~~~
- ### 字符串测试　

---
字符串测试是错误捕获很重要的一部分，特别在测试用户输入或比较变量时尤为重要。字符串测试有5种格式。
~~~
test "string"
test string_operator "string"
test "string" string_operator "string"
[string_operator string]
[string string_operator string]

这里，string_operator可为：
=       两个字符串相等。
!=      两个字符串不等。
-z      空串。
-n      非空串。
~~~
~~~
$[ -z $STRING ]
$echo $?
~~~
- ### 测试数值

---
测试数值可以使用许多操作符，一般格式如下：
~~~
"number" numseric_operator "number"
或者
["number" numberic_operator "number"]

numeric_operator可为：
-eq   数值相等。
-ne   数值不相等。
-gt   第一个数大于第二个数。
-lt   第一个数小于第二个数。
-le   第一个数小于等于第二个数。
-ge   第一个数大于等于第二个数。
~~~
~~~
$[ "100" -eq "99" ]
$echo $?
~~~
- ### expr用法　

---
expr命令一般用于整数值，但也可用于字符串。一般格式为：
~~~
expr arqument operator argument 
~~~
expr也是一个手工命令行计数器。
~~~
$expr 10 \* 10
$echo $?
#增量计数
$LOOP=0
$LOOP=`expr $LOOP + 1`
#数值测试
$VALUE=12
$expr $VALUE + 10 > /dev/null 2>&1
$echo $?
#模式匹配
$expr account.doc : '.*'
~~~
