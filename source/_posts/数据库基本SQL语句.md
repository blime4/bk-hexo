---
title: 数据库基本SQL语句
tags: sql
abbrlink: 21077b3b
date: 2020-07-28 11:32:11
---


# 数据库基本----SQL 语句大全 

## 一、基础 

###  创建数据库     
Create DATABASE database-name 

###  删除数据库     
drop database dbname 

###  备份 sql server 
> 创建 备份数据的 device 

USE master     
EXEC sp_addumpdevice 'disk', 'testBack', 'c:\mssql7backup\MyNwind_1.d at'
> 开始 备份 

BACKUP DATABASE pubs TO testBack 

###  创建新表 

create table tabname(col1 type1 [not null] [primary key],col2 typ e2 [not null],..) 

> 根据已有的表创建新表： 

A：create table tab_new like tab_old (使用旧表创建新表)     
B：create table tab_new as select col1,col2… from tab_old defini tion only 

###  删除新表     
drop table tabname 

###  增加一个列     
Alter table tabname add column col type 
> 注：列增加后将不能删除。DB2 中列加上后数据类型也不能改变，唯一能改变的是增 加 varchar 类型的长度。 

###  添加删除主键： 

Alter table tabname add primary key(col) 

Alter table tabname drop primary key(col) 

###  创建删除索引：

create [unique] index idxname on tabname(col….)     
drop index idxname     
> 注：索引是不可更改的，想更改必须删除重新建。 

###  创建删除视图：

create view viewname as select statement

drop view viewname 

###  几个简单的基本的 sql 语句 
    + 选择：select * from table1 where 范围     
    + 插入：insert into table1(field1,field2) values(value1,value2)     
    + 删除：delete from table1 where 范围     
    + 更新：update table1 set field1=value1 where 范围     
    + 查找：select * from table1 where field1 like ’%value1%’ ---like 的语法很精妙，查资料!     
    + 排序：select * from table1 order by field1,field2 [desc]
    + 总数：select count as totalcount from table1     
    + 求和：select sum(field1) as sumvalue from table1     
    + 平均：select avg(field1) as avgvalue from table1     
    + 最大：select max(field1) as maxvalue from table1     
    + 最小：select min(field1) as minvalue from table1


###  几个高级查询运算词 
+ UNION
> UNION 运算符通过组合其他两个结果表（例如 TABLE1 和 TABLE2）并消去表中 任何重复行而派生出一个结果表。当 ALL 随 UNION 一起使用时（即 UNION ALL），不消 除 重复行。两种情况下，派生表的每一行不是来自 TABLE1 就是来自 TABLE2。
+ EXCEPT 
> EXCEPT 运算符通过包括所有在 TABLE1 中但不在 TABLE2 中的行并消除所有 重复行而派生出一个结果表。当 ALL 随 EXCEPT 一起使用时 (EXCEPT ALL)，不消除重复 行。
+ INTERSECT 
> INTERSECT 运算符通过只包括 TABLE1 和 TABLE2 中都有的行并消除所有重复 行而派生出一个结果表。当 ALL 随 INTERSECT 一起使用时 (INTERSECT ALL)，不消除重 复行。注：使用运算词的几个查询结果行必须是一致的。 


###  使用外连接
+   left outer join
> 左外连接（左连接）：结果集既包括连接表的匹配行，也包括左连接表的所有行。     SQL: select a.a, a.b, a.c, b.c, b.d, b.f from a LEFT OUT JOI N b ON a.a = b.c 
+   right outer join
> 右外连接(右连接)：结果集既包括连接表的匹配连接行，也包括右连接表的所有行。
+   full outer join：     
> 全外连接：不仅包括符号连接表的匹配行，还包括两个连接表中的所有记录。 


## 提升

### 复制表      (只复制结构,源表名：a 新表名：b) (Access 可用) 

    + select * into b from a where 1<>1 
    + select top 0 * into b from a

### 拷贝表      (拷贝数据,源表名：a 目标表名：b) (Access 可用) 

    insert into b(a, b, c) select d,e,f from b; 

### 跨数据库之间表的拷贝        (具体数据使用绝对路径) (Access 可用) 

    insert into b(a, b, c) select d,e,f from b in ‘具体数据库’ w here 条件     
    例子：..from b in '"&Server.MapPath("."&"\data.mdb" &"' where..

### 子查询

    select a,b,c from a where a IN (select d from b   
    或者: sel ect a,b,c from a where a IN (1,2,3)


### between 

    select * from table1 where time between time1 and time2

    select a,b,c, from table1 where a not between 数值 1 and 数值 2


### 日程安排提前五分钟提醒

    select * from 日程安排 where datediff(‘minute’,f开始时间,getdate())>5


### 随机取出 10 条数据 
    select top 10 * from tablename order by newid() 

### 初始化表 table1     
    TRUNCATE TABLE table1 

### 选择从 10 到 15 的记录

    select top 5 * from (select top 15 * from table order by i d asc) table_别名 order by id desc 


## 技巧

### 1=1，1=2

    “where 1=1” 是表示选择全部   “where 1=2”全部不选

### 收缩数据库 

    --重建索引 
        DBCC REINDEX     
        DBCC INDEXDEFRAG     
    --收缩数据和日志     
        DBCC SHRINKDB     
        DBCC SHRINKFILE 

### 压缩数据库 

    dbcc shrinkdatabase(dbname) 


算了，后面我也不会