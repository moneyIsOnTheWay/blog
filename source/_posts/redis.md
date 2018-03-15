---
title: redis
date: 2017-12-22 14:13:35
categories: NoSQL
---
### 概述

#### 高性能键值对数据库，支持的键值数据类型

 1. 字符串类型
 2. 列表类型
 3. 有序集合类型
 4. 散列类型
 5. 集合类型

----------

#### 应用场景

 1. 缓存
 2. 任务队列
 3. 网站访问统计
 4. 数据过期处理
 5. 应用排行榜
 6. 分布式集群架构中的session分离
 
----------
#### 安装

> docker 安装redis
docker run --name redis -d redis

进入redis：
> docker exec -it redis bash
cd /usr/local/bin

启动客户端连接
> ./redis-cli

基本操作
> set key value
get key
