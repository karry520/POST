---
title: Git常用命令速查
mathjax: true
date: 2018-01-29 14:45:42
tags: github
---
- ### 创建版本库

---
~~~
git clone <url> 
git init
~~~
- ### 修改和提交

---
~~~
git status
git diff
git add 
git add <file>
git mv  <old><new>
git rm  <file>
git rm -m "commit message"
git commit --amend
~~~

- ### 查看提交历史

---
~~~
git log 
git log -p <file>
git blame  <file>
~~~

- ### 撤消

---
~~~
git reset --hard HEAD
git checkout HEAD <file>
git revert <commit>
~~~

- ### 分支与标签

---
~~~
git branch 
git checkout  <branch/tag>
git branch    <new-branch>
git branch -d <branch>
git tag 
git tag    <tagname>
git tag -d <tagname>
~~~

- ### 合并与衍合

---
~~~
git merge  <branch>
git rebase <branch>
~~~

- ### 远程操作

---
~~~
git remove -v 
git remove show <remote>
git remove add  <remote><url>
git fetch <remote>
git pull  <remote><branch>
git push  <remote><branch>
git push  <remote>:<branch/tag-name>
git push --tags
~~~

