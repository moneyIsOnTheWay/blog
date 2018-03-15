---
title: ssh终端下运行jar程序
date: 2018-02-21 21:59:23
tags: reverse
categories: Linux
---
## Linux运行jar包
> java -jar xxx.jar
## 后台运行
> java -jar xxx.jar &
## ssh终端下要改成如下
> nohup java -jar xxx.jar >temp.txt &

> nohup 意思是不挂断运行命令,当账户退出或终端关闭时,程序仍然运行 

``` >temp.txt```是将控制台输出定向到temp.txt文件中
