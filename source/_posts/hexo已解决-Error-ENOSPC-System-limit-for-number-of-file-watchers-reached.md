---
title: '[hexo已解决]  Error: ENOSPC: System limit for number of file watchers reached'
tags:
  - bug
  - hexo
categories: Tutorial
abbrlink: 94e5678c
date: 2020-06-20 03:16:56
---


输入`hexo cl && hexo g && hexo s`的时候 突然报出这个错误
> Error: ENOSPC: System limit for number of file watchers reached
吓得我按照他的指示，删了很多空文件夹都解决不了

然后[百度得知](http://blog.sina.com.cn/s/blog_507983580102zalu.html)
这是因为
>  是文件监视程序的系统产生了限制，达到了默认的上限，需要增加限额永久增加限额

然后找到了[解决方案](https://www.jianshu.com/p/4d2edd55b471)

在终端按顺序执行下面两个命令即可解决问题
```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
sudo sysctl --system
```