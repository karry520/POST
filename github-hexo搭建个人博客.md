---
title: github+hexo搭建个人博客
date: 2018-01-18 16:12:15
tags: github
mathjax: true
---

## hexo的安装
-	### 安装Git
>$ sudo apt-get install git
-	### 安装node.js
>$ curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
$ sudo apt-get install -y nodejs
-	### 安装hexo
>npm install -g hexo-cli

## hexo的使用
-	### 常用命令
>hexo n "我的博客" == hexo new "我的博客" #新建文章
hexo p == hexo publish
hexo g == hexo generate#生成
hexo s == hexo server #启动服务预览
hexo d == hexo deploy#部署

## 改变theme
-	### 使用Jacman主题
>$ git clone https://github.com/wuchong/jacman.git themes/jacman
-	### 修改配置文件_config.yml
>theme: jacman
stylus:
	compress: true

## 部署网站
-	### 安装工具
> npm install hexo-deployer-git --save
-	### 修改_config.yml
>deploy:
  type: git
  repository: Git URL 
  branch: master
  -	### 部署
  >hexo d
  
## TEX测试
>$$ \sum a_1 + \dots + a_n = S_n $$
