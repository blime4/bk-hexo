---
title: manjaro 安装mysql
tags:
  - manjaro
  - mysql
categories: sql
cover: 'https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo/2020-6-17/KugWYViSEHn5caR.jpg'
abbrlink: a07f0666
date: 2020-06-14 17:46:34
---

```
sudo pacman -S mysql

```



## 初始化

```
sudo mysqld --initialize --user=mysql --basedir=/usr --datadir=/var/lib/mysql

2019-08-01T14:02:29.538935Z 0 [Warning] [MY-010915] [Server] 'NO_ZERO_DATE', 'NO_ZERO_IN_DATE' and 'ERROR_FOR_DIVISION_BY_ZERO' sql modes should be used with strict mode. They will be merged with strict mode in a future release.
2019-08-01T14:02:29.538982Z 0 [System] [MY-013169] [Server] /usr/bin/mysqld (mysqld 8.0.16) initializing of server in progress as process 10795
2019-08-01T14:02:33.612822Z 5 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: zKaYIm!>x3aK
2019-08-01T14:02:35.009628Z 0 [System] [MY-013170] [Server] /usr/bin/mysqld (mysqld 8.0.16) initializing of server has completed

```

> 在安装输出的信息用，写着↑
>
> [basedir,datadir是什么](https://blog.csdn.net/wolfalcon/article/details/80528678)

> - 默认已经创建了一个 SQL 用户
>
> - 用户名： root@localhost
>
> - 密码：zKaYIm!>x3aK
>
>   这个密码是大家不一样的。看输出信息就可以知道密码是什么了





## 开机自启

```
sudo systemctl enable mysqld.service
```



## 启动 MySQL 服务

```
sudo systemctl start mysqld.service	
```

查看 MySQL 服务状态

```
systemctl status mysqld.service
```

输出如下： Active: active (running) 表示服务已经启动

```
● mysqld.service - MySQL Server
   Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; vendor preset: disabled)
   Active: active (running) since Thu 2019-08-01 22:03:15 CST; 34s ago
     Docs: man:mysqld(8)
           http://dev.mysql.com/doc/refman/en/using-systemd.html
  Process: 11218 ExecStartPre=/usr/bin/mysqld_pre_systemd (code=exited, status=0/SUCCESS)
 Main PID: 11235 (mysqld)
   Status: "SERVER_OPERATING"
    Tasks: 38 (limit: 4915)
   Memory: 373.0M
   CGroup: /system.slice/mysqld.service
           └─11235 /usr/bin/mysqld

```



## 连接数据库

```
mysql -uroot -p
```

输入刚刚的 密码即可连接成功

```
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 8.0.16

Copyright (c) 2000, 2019, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> 
```



## 修改密码

进入之后就改密码啦，初始化的密码太难记了

```sql
ALTER user 'root'@'localhost' IDENTIFIED BY 'new_password';
```







[ 参考](https://blog.csdn.net/qq_40829735/article/details/81166669)

[链接](https://blog.csdn.net/Bruce_Chou/article/details/85081721)


