---
title: Docker搭建MySQL的PHPMyAdmin的web管理界面
date: 2018-01-30 14:07:56
tags: reverse
categories: Docker
---
### Docker搭建MySQL的PHPMyAdmin的web管理界面

> 拉取一个mysql的镜像
`docker pull mysql`

> 启动并设置mysql的root密码
`docker run --name db -e MYSQL_ROOT_PASSWORD=123456 -p 3306:3306 -d mysql`

> 拉取一个phpmyadmin的镜像
`docker pull phpmyadmin/phpmyadmin`

>启动该镜像并设置相应的环境env
`docker run --name MySQLManage -d --link db:mysql -e PMA_HOST=mysql -p 8888:80 phpmyadmin/phpmyadmin`

>注意这里的PMA_HOST=mysql，在docker里面这里如果不指定的话，默认是localhost or 127.0.0.1那么phpmyadmin在连接mysql的时候就会报错
我就在这里在一次入坑了。～～
