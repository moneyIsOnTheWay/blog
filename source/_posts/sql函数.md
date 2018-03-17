---
title: sql函数
date: 2018-03-17 11:22:26
tags:
categories: SQL
---

### SQL函数

> 内建 SQL 函数的语法是：

```
SELECT function(列) FROM 表
```

- SQL SERVER 中的合计函数(Aggregate 函数的操作面向一系列的值，并返回一个单一的值。)

> AVG(column):返回某列的平均值

> COUNT(column(s)):返回某列/选中列的行数

> COUNT(DISTINCT column(s)): 返回非重复结果的数目

> FIRST(column): 函数返回指定的字段中第一个记录的值。

> LAST(column):  函数返回指定的字段中最后一个记录的值。

> MAX(column)： 返回某列的最高值

> MIN(column):返回某列的最低值

> SUM(column):返回某列的总和

- Scalar 函数(Scalar 函数的操作面向某个单一的值，并返回基于输入值的一个单一的值。)

> UCASE(c)	将某个域转换为大写

> LCASE(c)	将某个域转换为小写

> MID(c,start[,end])	从某个文本域提取字符

> LEN(c)	返回某个文本域的长度

> INSTR(c,char)	返回在某个文本域中指定字符的数值位置

> LEFT(c,number_of_char)	返回某个被请求的文本域的左侧部分

> RIGHT(c,number_of_char)	返回某个被请求的文本域的右侧部分

> ROUND(c,decimals)	对某个数值域进行指定小数位数的四舍五入

> MOD(x,y)	返回除法操作的余数

> NOW()	返回当前的系统日期

> FORMAT(c,format)	改变某个域的显示方式

> DATEDIFF(d,date1,date2)	用于执行日期计算


### GROUP BY

> GROUP BY 语句用于结合合计函数，根据一个或多个列对结果集进行分组

- SQL GROUP BY 实例
我们拥有下面这个 "Orders" 表：

```
O_Id	OrderDate	OrderPrice	Customer
1	2008/12/29	1000	Bush
2	2008/11/23	1600	Carter
3	2008/10/05	700	Bush
4	2008/09/28	300	Bush
5	2008/08/06	2000	Adams
6	2008/07/21	100	Carter
```

> 现在，我们希望查找每个客户的总金额（总订单）。我们想要使用 GROUP BY 语句对客户进行组合。我们使用下列 SQL 语句：

```
select Customer, SUM(OrderPrice) from Orders group by Customer
```

- SQL HAVING()

> 现在，我们希望查找每个用户有多个订单记录并统计订单数

```
select Customer,COUNT(Customer) as OrderNumber from Orders group by Customer having COUNT(Customer)>1
```

- UCASE()

> UCASE 函数把字段的值转换为大写。

```
SELECT UCASE(column_name) FROM table_name
```

- LCASE()

> LCASE 函数把字段的值转换为小写。

```
SELECT LCASE(column_name) FROM table_name
```

- MID() 函数

> MID 函数用于从文本字段中提取字符。

```
SELECT MID(column_name,start[,length]) FROM table_name
```
###### Persons表
```
Id	LastName	FirstName	Address	City
1	Adams	John	Oxford Street	London
2	Bush	George	Fifth Avenue	New York
3	Carter	Thomas	Changan Street	Beijing
```
> 我们希望从 "City" 列中提取前 3 个字符。

```
select MID(City,1,3) from Persons
```

> 结果如下

```
SmallCity
Lon
New
Bei
```