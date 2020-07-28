---
title: ubuntu mysql5.7 统一 utf8
tags:
  - ubuntu
  - mysql
abbrlink: c5e8d58e
date: 2020-07-26 13:26:06
---

[Ubuntu中MySQL5.7设置utf8编码格式步骤](https://blog.csdn.net/qq_32144341/article/details/51318390/)

+ vim /etc/mysql/mysql.conf.d
> 在`lc-messages-dir = /usr/share/mysql` 语句后添加 `character-set-server=utf8 `
+ vim /etc/mysql/conf.d/mysql.cnf
> 添加`default-character-set=utf8`
+ /etc/init.d/mysql restart