---
title: vscode远程连接jupyter
tags:
  - vscode
  - jupyter
categories: Tutorial
abbrlink: 639fb620
date: 2020-06-26 12:58:11
---




> 其实我直接输入`jupyter notebook --allow-root`就直接可以用了。下面看看另外的方法

### 安装
```
pip install jupyter
```

### 远程连接配置

终端打开ipython
输入以下：
```
from notebook.auth import passwd
passwd()
# 然后按照操作输入密码（这个密码是你以后登录notebook时使用的密码）
# 输入之后就会得到一串字符，要记住这个字符，后面会用到


exit()
```

终端输入：
```
jupyter notebook --generate-config
vim ~/.jupyter/jupyter_notebook_config.py
```

修改配置文件
找到如下命令修改

```
c.NotebookApp.ip = '*'
#设置可访问的ip为任意。   这里我是保留为c.NotebookApp.ip = 'localhost'
c.NotebookApp.open_browser = False
#设置默认不打开浏览器  这一步我觉得也是多余的
c.NotebookApp.password = '第1步生成的密文'   刚刚的密文
 
c.NotebookApp.port = 6666    
# 其他端口也可以

```


### 最后

终端输入
```
jupyter notebook --allow-root
```
就可以了




### debug

此网址使用了一个通常用于网络浏览以外目的的端口。出于安全原因，Firefox 取消了该请求。

+ 在Firefox地址栏输入 about:config
+ 在搜索框输入`network.security.ports.banned.override`
+ 选择为字符串
+ 输入刚刚配置的端口号`6666`
+ 就ok了













> 参考链接：
[此网址使用了一个通常用于网络浏览以外目的的端口。出于安全原因，Firefox 取消了该请求。](https://blog.csdn.net/xiaojin21cen/article/details/84920327)
[Jupyter Notebook 远程连接及配置方法说明](https://www.jianshu.com/p/08f276d48669?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)