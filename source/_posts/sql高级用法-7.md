---
title: sql高级用法-7
date: 2018-03-16 17:17:44
tags:
categories: SQL
---
### SQL Date函数

- MySQL Date 函数

  - NOW():返回当前的日期和时间
  - CURDATE():返回当前的日期
  - CURTIME():返回当前的时间
   ``` 
   SELECT NOW(),CURDATE(),CURTIME()
   ```
    2008-12-29 16:25:46	2008-12-29	16:25:46
   
   ```
   CREATE TABLE Orders (
   OrderId int NOT NULL,
   ProductName varchar(50) NOT NULL,
   OrderDate datetime NOT NULL DEFAULT NOW(),
   PRIMARY KEY (OrderId)
   )
   ```
    请注意，OrderDate 列规定 NOW() 作为默认值。作为结果，当您向表中插入行时，当前日期和时间自动插入列中。
  - DATE():提取日期或日期/时间表达式的日期部分
  
  ```
  SELECT ProductName, DATE(OrderDate) AS OrderDate
  FROM Orders
  WHERE OrderId=1
  ```
  - EXTRACT():返回日期/时间按的单独部分
  
   假设有表order(OrderId int,productname varchar(255),orderdate datetime)
   ## 表内容： 1	'Computer'	2008-12-29 16:25:46.635
  
  ```
  select extract(year from orderdate) as orderyear,
  extract(month from orderdate) as ordermonth,
  extract(day from orderdate) as orderday
  from order where OrderId=1
  ```
  ## sql结果: 2008	12	29
  
  - DATE_ADD():给日期添加指定的时间间隔
  
   ## 语法:DATE_ADD(date,INTERVAL expr type)
   date 参数是合法的日期表达式。expr 参数是您希望添加的时间间隔。
   ## "OrderDate" 添加 2 天
   ```
   SELECT OrderId,DATE_ADD(OrderDate,INTERVAL 2 DAY)
   AS OrderPayDate
   FROM Orders
   ```
  - DATE_SUB():从日期减去指定的时间间隔
  - DATEDIFF():返回两个日期之间的天数
  
  ```
  SELECT DATEDIFF('2008-12-30','2008-12-29') AS
  DiffDate
  ```
  
  ## 1
  
  ```
  SELECT DATEDIFF('2008-12-29','2008-12-30') AS
  DiffDate
  ```
  
  ## -1
  - DATE_FORMAT():用不同的格式显示日期/时间
  
  ```
  DATE_FORMAT(date,format)
  ```
  
  ```
  DATE_FORMAT(NOW(),'%b %d %Y %h:%i %p')
  DATE_FORMAT(NOW(),'%m-%d-%Y')
  DATE_FORMAT(NOW(),'%d %b %y')
  DATE_FORMAT(NOW(),'%d %b %Y %T:%f')
  ```
  
  ```
  Dec 29 2008 11:45 PM
  12-29-2008
  29 Dec 08
  29 Dec 2008 16:25:46.635
  ```
  
### SQL SERVER DATE 函数


######  函数	描述

- GETDATE()	返回当前日期和时间
- DATEPART()	返回日期/时间的单独部分
- DATEADD()	在日期中添加或减去指定的时间间隔

```
DATEADD(datepart,number,date)
```

```
SELECT OrderId,DATEADD(day,2,OrderDate) AS OrderPayDate
FROM Orders
```
- DATEDIFF()	返回两个日期之间的时间

```
DATEDIFF(datepart,startdate,enddate)
```

- CONVERT()	用不同的格式显示日期/时间