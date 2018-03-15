---
title: 学习docker遇到的坑
date: 2017-12-22 17:30:53
tags: reverse
categories: Docker
---
# Docker用yml文件管理项目时要注意

 - 构建nginx+PHP+MySQL（在一个yml中管理的）的容器时发现PHP程序链接不上MySQL，抱各种错误，而我自己用MySQL的客户端工具去链接docker容器中的MySQL服务却能正常链接，就很纳闷
 - 在PHP程序中改host：127.0.0.1不行，localhost也不行，就试下链接云主机上的docker容器的MySQL服务，没想到成功链接上了，就排除不是PHP程序本身的问题，那么是啥的问题？
 - 答案就是host错误了，不是127.0.0.1或者localhost，那么host该是啥？
 - 看了docker官网讲yml文件容器的网络问题，提到network标签，MySQL对容器内的其他程序是以mysql访问的，即host=mysql，完美解决。就这一个小问题折腾了我一下午，谨记。
