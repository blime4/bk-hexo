---
title: numpy的广播机制
tags: numpy
categories: Tutorial
abbrlink: 9c94136a
date: 2020-06-22 15:28:42
---

参考
[一文读懂NumPy中的广播机制](https://finthon.com/numpy-broadcast/)
《利用python进行数据分析》 第十一章 广播 


## 引出
> 在NumPy中如果遇到大小不一致的数组运算，就会触发广播机制。满足一定的条件才能触发广播，不然也会报错。

就是在进行加减乘运算的时候，如果两个数组大小不一样，有一些是可以触发广播机制来进行运算的。

## 那些可以触发呢

### 数组维度不同，后缘维度的轴长相符
> 后缘维度: trailing dimension 即从末尾开始算起的维度
> 例如： (5,4,3,2,1) 的后缘维度可以是，(1),(2,1),(3,2,1),(4,3,2,1),(5,4,3,2,1)

例子：

x1 = np.random.randint(0,4,(4,3))
x2 = np.random.randint(0,4,(3,))

x1 + x2 是可以直接相加的

例图：
![](https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo@master/2020-6-22/1.png)
同样的例子还有：
![](https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo@master/2020-6-22/2.png)

### 数组维度相同，其中有个轴为1
> 例子： 
x1 = np.random.randint(0,4,(4,3))
x2 = np.random.randint(0,4,(4,1))


x1 + x2 也是可以直接相加的

例图：
![](https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo@master/2020-6-22/3.png)