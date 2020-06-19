---
title: manjaro 在命令行打开文件夹
tags:
  - manjaro
  - cmd
categories: chaos
cover: 'https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo/2020-6-17/ykDlWYh9zBai2nv.jpg'
abbrlink: a77e179e
date: 2020-06-14 17:44:52
---


命令行输入

```
dolphin .
```

就可以了。
（这是随便尝试发现的，有更好的方法也可以写在评论上）




为了方便。

我们把它写进～/.zshrc文件中（或者你的是 ～/.bashrc)

```
sudo vim ~/.zshrc

#加入下面这句，我们用open代替

alias open='dolphin .'

#然后激活

source ~/.zshrc
```









如果是Ubuntu的话，输入这句
```
nautilus .
```