---
title: ubuntu mysql5.7 统一 utf8
tags:
  - ubuntu
  - mysql
abbrlink: c5e8d58e
date: 2020-07-26 13:26:06
---

[Ubuntu?MySQL5.7??utf8??????](https://blog.csdn.net/qq_32144341/article/details/51318390/)

+ vim /etc/mysql/mysql.conf.d
> ?`lc-messages-dir = /usr/share/mysql` ????? `character-set-server=utf8` ??
<br>
+ vim /etc/mysql/conf.d/mysql.cnf
> ??`default-character-set=utf8`
<br>
+ /etc/init.d/mysql restart