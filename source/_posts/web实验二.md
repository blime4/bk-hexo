---
title: web实验二
tags:
  - web
  - 实验
  - 作业
categories: 作业
hide: true
abbrlink: 579b49e3
date: 2020-07-05 03:51:41
---

# 实验1 简易计算器的制作

<link rel="stylesheet" href="/css/calculator.css" />
<body>
    <div id="calculator">
        <!-- Screen and clear key -->
        <div class="top">
            <span class="clear">C</span>
        <div class="screen"></div>
    </div>
    <div class="keys">
        <!-- operators and other keys -->
        <span>7</span>
        <span>8</span>
        <span>9</span>
        <span class="operator">+</span>
        <span>4</span>
        <span>5</span>
        <span>6</span>
        <span class="operator">-</span>
        <span>1</span>
        <span>2</span>
        <span>3</span>
        <span class="operator">÷</span>
        <span>0</span>
        <span>.</span>
        <span class="eval">=</span>
        <span class="operator">x</span>
        </div>
    </div>
    <script src="/js/calculator.js"></script>
</body>

<br>
<br>

# 实验2：控制网页字体的太小


<div>
<style>
    a {
        text-decoration: none;
        color: #000
    }    
    a:hover {
        color: #F36
    }
</style>

<link href="https://cdn.bootcss.com/twitter-bootstrap/4.5.0/css/bootstrap.min.css" rel="stylesheet">

<body id="changecolor">        
        <section  style="margin: 0 auto;width: 900px;text-align: center;">
            <br>
            <br>
            <br>
            <br>
            <br>
            <br>
            <h2>电影里有哪些让你念念不忘的经典台词？</h2>
            <!-- <div class="btn-group" role="group" aria-label="Basic example">
                <button type="button" class="btn btn-secondary" a href="javascript:changesize('26')" >大</button>
                <button type="button" class="btn btn-secondary" a href="javascript:changesize('20')" > 中</button>
                <button type="button" class="btn btn-secondary" a href="javascript:changesize('12')" >小</button>
            </div> -->
            <p>字体调节：
                <a class="btn btn-secondary" href="javascript:changesize('26')">大</a>
                <a class="btn btn-secondary" href="javascript:changesize('20')">中</a>            
                <a class="btn btn-secondary" href="javascript:changesize('12')">小</a>        
            </p>
            <p id="changesize">
            <br>
            如果我有的选，我能比你们所有人都好。——《何以为家》
            <br>
            <br>
            世界上有太多孤独的人，害怕先踏出第一步。——《绿皮书》
            <br>
            <br>
            很多时候，蒙蔽我们双眼的，不是假象，而是自己的执念。——《赎罪》
            <br>
            <br>
            有些东西值得失去，因为我们会永远记得。——《时时刻刻》
            <br>
            <br>
            在你想要放弃的那一刻，想想为什么当初坚持走到这里。——《美国丽人》
            <br>
            <br>
            人们彼此疏远，内心却支离破碎。——《超脱》
            </p>
            <br>
        </section>
        <script>
            function changesize(size) {
                document.getElementById("changesize").style.fontSize = size + "px";
            }
        </script>
    </body>
</div>

