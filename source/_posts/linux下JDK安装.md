---
title: linux下jdk安装
date: 2017-01-20 17:25:39
tags: tools
categories: Java
---
# linux下jdk环境配置

---

 1. jdk官网下载jdk的版本安装包，fedora我下载的是Linux x64的tar.gz包
 2. 解压到你要安装的本地目录中，我这里是解压到/usr/java下
 3. 打开终端直接快捷Ctrl+Alt+t切换到root用户vim编辑/etc/profile文件，添加

    * export JAVA_HOME=/home/wy/enviorment/Java/jdk1.8.0_151*
    * export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar*
    * export PATH=$PATH:$JAVA_HOME/bin:$PATH*

 4. 保存退出vim执行source /etc/profile
 5. 在终端输入java -version出现如下提示则说明安装正确
  ~\$ java -version
    Picked up _JAVA_OPTIONS:   -Dawt.useSystemAAFontSettings=gasp
    java version "1.8.0_144"
    Java(TM) SE Runtime Environment (build 1.8.0_144-b01)
    Java HotSpot(TM) 64-Bit Server VM (build 25.144-b01, mixed mode)
 6. 注销当前登录，重新登录就可生效
