---
title: web实验三
tags:
  - web
  - 实验
  - 作业
categories: 作业
hide: true
abbrlink: 15c7dfee
date: 2020-07-05 04:48:26
---


> 由于一些憨憨的决定，我使用了window来做实验三

# 实验1 配置JSP运行环境

## 下载安装JDK9.0.1

下载的方法就是直接去官网下载。
然后配置环境变量。
```
JAVA_HOME  C:\Program Files\Java\jdk-9.0.1
JRE_HOME   C:\Program Files\Java\jre-9.0.1
CLASS_PATH .;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;
Path       %JAVA_HOME%\bin
           %JRE_HOME%\bin
```
![](https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo/2020-7-5/2.png)
验证是否成功

```
java -version 
javac -version 
```

## 下载安装Tomcat/9.0.36

下载的方法就是直接去官网下载。
然后配置环境变量。

```
CATALINA_HOME     D:\itapp\tomcat
TOMCAT_HOME       D:\itapp\tomcat
Path              %TOMCAT_HOME%\bin
                  %CATALINA_HOME%\lib
```


## 验证是否搞定JSP运行环境

cmd中输入`startup`，然后在浏览器打开`http://127.0.0.1:8080/`,或者`localhost:8080`
出现这样的tomcat界面，就说明成功了


![](https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo/2020-7-5/1.png)



# 实验2：网上购物订单的制作

参考的一些链接：  
[eclipse中没有server选项解决方法](https://www.jb51.net/softjc/550232.html)
[将 Tomcat 和 Eclipse 相关联](https://www.runoob.com/jsp/eclipse-jsp.html)

> 这里要注意就是，在右下角可以看到安装进步，不是按了`finish`就安装完了，右下角安装完，会提示`reload`的


