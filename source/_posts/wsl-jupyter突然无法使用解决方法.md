---
title: wsl jupyter突然无法使用解决方法
tags:
  - wsl
  - jupyter
  - bug
categorites: bug
abbrlink: 6c1f2f8b
date: 2020-07-10 11:47:26
---

试了很多方法，包括重装了，都不可以

然后就找到了一个解决方案


```
jupyter notebook --ip=0.0.0.0

```

然后就解决了
