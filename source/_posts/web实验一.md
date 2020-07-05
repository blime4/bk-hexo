---
title: web实验一
tags:
  - web
  - 实验
  - 作业
categories: 作业
hide: true
abbrlink: 6c1b674a
date: 2020-07-04 23:20:03
---

# 实验1 个人简历

谢绍波的个人简历

## 个人信息
- **姓名：** 谢绍波
- **性别：** 男
- **学校专业：** **广州大学**计算机科学与技术
- **blog：** https://blime4.github.io/
- **Email：** 13192551898@163.com
- **QQ/微信号：** 1063494564/19927577007


## 技能清单


- 编程语言：python，c++
- 计算平台：Hadoop，Spark
- 前端框架：Bootstrap/Angular
- 机器学习模型/算法框架：GBDT/LR/SVM、Tensorflow/PyTorch
- 数据库相关：MySQL/PgSQL/SQLite
- 版本管理、文档和自动化部署工具：Git

## 项目经历
+ 基于GAN的AI 作曲
+ 基于yolov3的口罩检测系统
  
## 获奖经历
+ ACM省赛铜奖
    
---      
## 致谢
感谢您花时间阅读我的简历，期待能有机会和您共事。
<br>
<br>


# 实验2 一个月消费表



<script src="https://cdn.bootcss.com/echarts/4.2.1-rc1/echarts.min.js"></script>
  <!-- 为ECharts准备一个具备大小（宽高）的Dom -->
<div id="main" style="width: 600px;height:400px;"></div>
<script >
    var myChart = echarts.init(document.getElementById('main'));
    var option = {
        title: {
            text: '大学一个月消费表',
            subtext: 'demo',
            left: 'center'
        },
        tooltip: {
            trigger: 'item',
            formatter: '{a} <br/>{b} : {c} ({d}%)'
        },
        legend: {
            left: 'center',
            top: 'bottom',
            data: ['吃喝', '购物', '通讯', '出行', '学习', '其他']
        },
        toolbox: {
            show: true,
            feature: {
                mark: {show: true},
                dataView: {show: true, readOnly: false},
                magicType: {
                    show: true,
                    type: ['pie', 'funnel']
                },
                restore: {show: true},
                saveAsImage: {show: true}
            }
        },
        series: [
            {
                name: '面积模式',
                type: 'pie',
                radius: [30, 110],
                center: ['50%', '50%'],
                roseType: 'area',
                data: [
                    {value: 100, name: '吃喝'},
                    {value: 50, name: '购物'},
                    {value: 150, name: '通讯'},
                    {value: 250, name: '出行'},
                    {value: 200, name: '学习'},
                    {value: 70, name: '其他'}
                ]
            }
        ]
    };
    myChart.setOption(option);
</script>

| 分类 | 消费 |
| ---- | ---- |
| 吃喝 | 100  |
| 购物 | 50   |
| 通讯 | 150  |
| 出行 | 250  |
| 学习 | 200  |
| 其他 | 70   |


# 实验3 表单制作注册页面

<link href="https://cdn.bootcss.com/twitter-bootstrap/4.5.0/css/bootstrap.min.css" rel="stylesheet">
<div class="modal-dialog" style="margin-top: 10%;">
    <div class="modal-content">
      <div class="modal-header">
        <h4 class="modal-title text-center" id="myModalLabel">blime邮件注册</h4>
      </div>
      <div class="modal-body" id = "model-body">
        <form>
        <div class="form-group">
          <label for="exampleInputname">昵称</label>
          <input type="name" class="form-control" id="exampleInputname">
        </div>
        <div class="form-group">
          <label for="exampleInputsex">性别</label>
          <input type="name" class="form-control" id="exampleInputsex">
        </div>
        <div class="form-group">
          <label for="exampleInputEmail1">邮箱地址</label>
          <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
          <small id="emailHelp" class="form-text text-muted">We'll never share your email with anyone else.</small>
        </div>
        <div class="form-group">
          <label for="exampleInputPassword1">密码</label>
          <input type="password" class="form-control" id="exampleInputPassword1">
        </div>
        <div class="form-group">
          <label for="exampleInputPassword1">确认密码</label>
          <input type="password" class="form-control" id="exampleInputPassword1">
        </div>
        <div class="form-group form-check">
          <input type="checkbox" class="form-check-input" id="exampleCheck1">
          <label class="form-check-label" for="exampleCheck1">我已阅读***</label>
        </div>
        <button type="submit" class="btn btn-primary">注册</button>
        </form>
      </div>
    </div>
</div><!-- /.modal -->


# 实验4 多重框架和超连接
<br>
<br>

> 做一个简单的多重框架，超链接相册集
<div class="row justify-content-md-center">
<div class="card mb-3" style="max-width: 540px;">
  <div class="row no-gutters">
    <div class="col-md-4">
      <img src="https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo@master/2020-7-5/6.jpg" class="card-img" alt="...">
    </div>
    <div class="col-md-8">
      <div class="card-body">
        <h5 class="card-title">哆啦A梦相册</h5>
        <p class="card-text">哆啦A梦，伴我同行</p>
        <p class="card-text">哆啦A梦，伴我同行</p>
        <p class="card-text">哆啦A梦，伴我同行</p>
        <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
      </div>
    </div>
  </div>
  <button type="button" class="btn btn-primary btn-lg btn-block">让我们进入相册吧</button>
</div>
</div>
<br>
<br>

# 实验5 利用CSS技术将一个HTML网页排版布局
<br>

> 如上四个实验，可以看出，运用了利用CSS技术将一个HTML网页排版布局
> 之所以把五个小实验放在一起，就是来做第五个实验，展示HTML网页排版布局