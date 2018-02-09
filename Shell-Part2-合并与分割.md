---
title: Shell-Part2-合并与分割
tags: Shell
date: 2018-02-01 09:59:49
---
有几种工具用来处理文本文件分类、合并和分割操作
- ### sort用法

---
sort命令将许多不同的域按不同的列顺序分类。sort命令的一般格式为：
~~~
sort -cmu -o output_file [other options] +pos1 +pos2 input_files
~~~
下面简要介绍一下sort的参数：
~~~
-c      测试文件是否已经分类。
-m      合并两个分类文件。
-u      删除所有复制行。
-o      存储sort结果的输出文件名。
其他选项有：
-b      使用域进行分类时，忽略第一个空格。
-n      指定分类是域上的数字分类。
-t      域分隔符；用非空格或tab键分隔域。
-r      对分类次序或比较求逆。
+n      n为域号。使用此域号开始分类。
n       n为域号。在分类比较时忽略此域，一般与+ n一起使用。
post1   传递到m，n。m为域号，n为开始分类字符数；例如4，6意即以第5域分类，从第7个字符开始。
~~~
- ### 系统sort

---
sort可以用来对/etc/passwd文件中用户名进行分类。
~~~
$cat passwd | sort -t: +0 | awk - F":" '{print $1}'
~~~
sort还可以用于df命令，以递减顺序打印使用列。
~~~
$df | sort -b -r +4 
~~~
- ### uniq用法　

---
uniq用来从一个文本文件中去除或禁止重复行。
~~~
#一般格式　
uniq -u d c -f input-file output-file
    -u  只显示不重复行
    -d  只显示有重复行只显示其中一行
    -c  打印每一重复行出现次数
    -f  n为数字，前n个域被忽略
~~~
~~~
$uniq -c 1.txt
~~~
- ### join用法

---
join用来将来自两个分类文本文件的行连在一起。
~~~
join [options] input-file1 input-file2
~~~
- ### cut用法

---
cut用来从标准输入或文本文件中剪切列或域。
~~~
$cut [option] file1 file2
~~~
- ##＃ paste用法　

---
cut用来从文本文件或标准输出中抽取数据列或者域，然后再用paste可以将这些数据粘贴起来形成相关文件。
~~~
$paste -d -s -file1 file2
~~~
- ### split用法　

---
split用来将大文件分割成小文件。有时文件越来越大，传送这些文件时，首先将其分割可能更容易。
~~~
$split -output_file-size input-file-name out-filename 
~~~
