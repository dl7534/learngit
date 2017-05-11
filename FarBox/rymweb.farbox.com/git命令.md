---
date: 2017-02-10 17:51
status: public
title: git命令
---

目的：记录整个项目的历史记录、版本
查看文件目录dir
进入文件夹cd
盘符：进入磁盘
> 1.git init 告知git接管（创建.git文件）

git status 监控文件夹的状态
> 2.git add index.html 指定文件夹归git接管
> 2.git add . 接管所有

git diff  查看修改的内容
git commit 提交
> 3.git commit -m"123" 强制添加注释并提交
第一个版本提交完成

git log 查看过往提交
git reset --hard HEAD^ 退回之前的版本
git reset --hard HEAD 版本号（--git log可以找到）
> 4.git push origin master 提交
> 5.git clone github中的地址（复制代码）

备注：
* $ git config --global user.name "your name"
* $ git config --global user.email "your_email@youremail.com"

1.告知接管
2.接管什么
3.提交完成接管