---
title: vim-配置
date: 2018-01-20 12:03:36
tags: Vim 
---

- ## vim配置

- ###	安装Bundle

- #### 	clone文件

> git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim

- #### 	修改配置文件~/.vimrc

> " vundle 环境设置
filetype off
    set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
    ...
    "要安装的插件列表
    ...
call vundle#end()
   filetype plugin indent on

- ### 	bundle命令
> BundleInstall 
BundleClean
BundleUpdate
BundleList
BundleSearch
- ### 	安装插件
- #### 	第一步：将要安装的插件添加到~/.vimrc列表中 
- ####	第二步：打开vim输入命令BundleInstall命令
- ### 	常规设置 
~~~
" 关闭与vi的兼容
set nocompatible
" 使用utf-8编码
set encoding=utf-8
" 总是显示状态栏
set laststatus=2
" 显示光标当前位置
set ruler
" 开启行号显示
set number
" 高亮显示当前行/列
set cursorline
set cursorcolumn
" 高亮显示搜索结果
set hlsearch
" 可以使用鼠标
set mouse=a
" 开启语法高亮功能
syntax enable
" 允许用指定语法高亮配色方案替换默认方案
syntax on
" 自适应不同语言的智能缩进
filetype indent on
~~~
- ### 	文字排版
~~~
" 将制表符扩展为空格
set expandtab
" 设置编辑时制表符占用空格数
set tabstop=4
" 设置格式化时制表符占用空格数
set shiftwidth=4
" 让 vim 把连续数量的空格视为一个制表符
set softtabstop=4
~~~
