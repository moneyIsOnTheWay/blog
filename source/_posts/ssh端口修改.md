---
title: ssh端口修改
date: 2018-02-21 22:32:35
tags: tools
categories: Linux
---
## 检查你打开了哪个端口
> netstat -an | grep -i listen 

## 修改默认ssh端口
> vi /etc/ssh/sshd_config

> 修改 #port 22 -> port 22  port xx此处先不关闭22端口

## 重启ssh服务
> service sshd restart

## 查看监听端口检查你设置的端口是否生效
> netstat -an | grep -i listen 

## 生效后将port 22 注销掉，重启ssh服务
> service sshd restart
