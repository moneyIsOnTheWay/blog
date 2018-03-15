---
title: linux日志系统问题
date: 2017-12-21 17:15:43
tags: server
categories: Linux
---
# centos下的日志系统问题

---

*不小心删除了/var/log/serure文件后日志记录不了了*

 1. 重启日志服务
 2. 重启ssh服务

*重启日志服务*

>service rsyslog restart

*重启ssh服务*

>service sshd restart

*日志文件太大要清空*

>echo "" > /var/log/secure

