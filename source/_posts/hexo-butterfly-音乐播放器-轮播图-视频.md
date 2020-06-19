---
title: hexo+butterfly+音乐播放器+轮播图+视频
tags:
  - hexo
  - butterfly
categories: Tutorial
sticky: 8
cover: 'https://cdn.jsdelivr.net/gh/blime4/jsd-for-hexo/2020-6-17/RFQyHh8Dek9CLsB.jpg'
abbrlink: deaa27b0
date: 2020-06-20 01:16:44
---


## 音乐播放器



{% meting "60198" "netease" "playlist" "autoplay" "mutex:false" "listmaxheight:140px" "preload:none" "theme:#ad7a86"%}

> 音乐播放器的代码如下
```
{% meting "60198" "netease" "playlist" "autoplay" "mutex:false" "listmaxheight:140px" "preload:none" "theme:#ad7a86"%}
```

+ 其中的数字 ：就是网页版网易对应的歌单的id
+ autoplay:就是默认自动播放
+ listmaxheight：就是显示列表的高度
+ preload：是否预加载
+ theme：主题色

## 轮播图

[参考链接](https://www.antmoe.com/posts/a811d614/index.html#%E8%BD%AE%E6%92%AD%E5%9B%BE)

轮播图的修改来源于网络（jq）的一个插件。此项修改引入 js 文件即可。
```
(function () {
  function Slider(option) {
    this.wrap = option.wrap;
    this.imgList = option.imgList;
    this.imgNum = this.imgList.length;
    this.width = option.width || $(this.wrap).width();
    this.height = option.height || $(this.wrap).height();
    this.isAuto = option.isAuto || true;
    this.moveTime = option.moveTime;
    this.direction = option.direction || "right";
    this.btnWidth = option.btnWidth;
    this.btnHeight = option.btnHeight;
    this.spanWidth = option.spanWidth;
    this.spanHeight = option.spanHeight;
    this.spanColor = option.spanColor;
    this.activeSpanColor = option.activeSpanColor;
    this.btnBackgroundColor = option.btnBackgroundColor;
    this.spanRadius = option.spanRadius;
    this.spanMargin = option.spanMargin;
    this.flag = false;
    this.nowIndex = 0;
    this.createDom();
    this.initStyle();
    this.bindEvent();
    if (this.isAuto === true) {
      this.autoMove();
    }
  }

  Slider.prototype.createDom = function () {
    var oUl = $('<ul class="imgList"></ul>');
    var Spot = $('<div class="spot"></div>');
    this.imgList.forEach(function (item) {
      var oLi =
        '<li><a  href=" ' +
        item.a +
        'target="_blank" "><img src=" ' +
        item.img +
        ' "></a></li>';
      oUl.append(oLi);
      var span = "<span></span>";
      Spot.append(span);
    });
    var leftBtn = $(
      '<div class="left-btn"><i class="fas fa-angle-left"></i></div>'
    );
    var rightBtn = $(
      '<div class="right-btn"><i class="fas fa-angle-right"></i></div>'
    );
    this.wrap.append(oUl).append(leftBtn).append(rightBtn).append(Spot);
  };
  Slider.prototype.initStyle = function () {
    $("*", this.wrap).css({ margin: 0, padding: 0, listStyle: "none" });
    $(this.wrap).css({ overflow: "hidden", position: "relative" });
    $(".imgList", this.wrap).css({
      width: this.width,
      height: this.height,
      position: "relative",
    });
    $(".imgList li", this.wrap)
      .css({
        width: this.width,
        height: this.height,
        position: "absolute",
        left: 0,
        top: 0,
        display: "none",
      })
      .eq(this.nowIndex)
      .css({ display: "block" });
    $(".imgList li a, .imgList li a img", this.wrap).css({
      display: "inline-block",
      width: this.width,
      height: this.height,
    });
    $(".left-btn, .right-btn", this.wrap).css({
      width: this.btnWidth,
      height: this.btnHeight,
      backgroundColor: this.btnBackgroundColor,
      color: "#fff",
      textAlign: "center",
      lineHeight: this.btnHeight + "px",
      position: "absolute",
      top: "50%",
      marginTop: -this.btnHeight / 2,
      cursor: "pointer",
    });
    $(".right-btn", this.wrap).css({ right: 0 });
    $(".spot", this.wrap).css({
      height: this.spanHeight + this.spanMargin * 2,
      position: "absolute",
      left: "50%",
      marginLeft: (-this.imgNum * (this.spanWidth + this.spanMargin * 2)) / 2,
      bottom: 10,
    });
    $(".spot span", this.wrap)
      .css({
        display: "inline-block",
        width: this.spanWidth,
        height: this.spanHeight,
        margin: this.spanMargin,
        backgroundColor: this.spanColor,
        borderRadius: this.spanRadius,
        cursor: "pointer",
      })
      .eq(this.nowIndex)
      .css({ backgroundColor: this.activeSpanColor });
  };
  Slider.prototype.bindEvent = function () {
    var self = this;
    $(".left-btn", this.wrap).click(function () {
      self.move("prev");
    });
    $(".right-btn", this.wrap).click(function () {
      self.move("next");
    });
    $(".spot span").click(function (e) {
      self.move($(this).index());
    });
    $(this.wrap).mouseenter(function () {
      clearInterval(self.time);
    });
  };
  Slider.prototype.move = function (dir) {
    if (this.flag) {
      return false;
    }
    this.flag = true;
    switch (dir) {
      case "prev":
        if (this.nowIndex === 0) {
          this.nowIndex = this.imgNum - 1;
        } else {
          this.nowIndex--;
        }
        break;
      case "next":
        if (this.nowIndex === this.imgNum - 1) {
          this.nowIndex = 0;
        } else {
          this.nowIndex++;
        }
        break;
      default:
        this.nowIndex = dir;
        break;
    }
    var self = this;
    $(".imgList li", this.wrap)
      .fadeOut()
      .eq(this.nowIndex)
      .fadeIn(function () {
        self.flag = false;
      });
    $(".spot  span", this.wrap)
      .css({ backgroundColor: this.spanColor })
      .eq(this.nowIndex % this.imgNum)
      .css({ backgroundColor: this.activeSpanColor });
  };
  Slider.prototype.autoMove = function () {
    var self = this;
    this.time = setInterval(function () {
      if (this.direction == "left") {
        $(".left-btn", this.wrap).trigger("click");
      } else {
        $(".right-btn", this.wrap).trigger("click");
      }
    }, self.moveTime);
  };
  $.fn.extend({
    slider: function (option) {
      option.wrap = this;
      new Slider(option);
    },
  });
})();

```

使用也很简单，只要在 md 文章中写入以下内容即可

```
<div class="demo"></div>
<script>
    function tt(){
        $('.demo').slider({
    imgList: [
        {
            img: 'https://cdn.jsdelivr.net/gh/blogimg/picbed@latest/2020/04/13/2a877ea5da1292c817cbc2a254c01c31.png',
            a: '跳转url地址',
        },
        {
            img: 'https://cdn.jsdelivr.net/gh/blogimg/picbed@latest/2020/04/13/5005109d1aa2ffd28984c2b02b8cbfbe.png',
            a: '跳转url地址',
        },
        {
            img: 'https://cdn.jsdelivr.net/gh/blogimg/picbed@latest/2020/04/13/163a2ade4361d1ed705ed523091af67e.png',
            a: '跳转url地址',
        }
    ], //图片的列表，a属性里面存放的是网络地址，img存放的是图片地址
    width: "100%", //图片的宽
    height: 500, //图片的高
    isAuto: false, //是否自动轮播
    moveTime: 3000, //运动时间
    direction: 'right', //轮播的方向
    btnWidth: 30, //按钮的宽
    btnHeight: 30, //按钮的高
    spanWidth: 10, //span按钮的宽
    spanHeight: 10, //span按钮的高
    spanColor: '#fff', //span按钮的颜色
    activeSpanColor: 'red', //选中的span颜色
    btnBackgroundColor: 'rgba(0, 0, 0, 0.3)', //两侧按钮的颜色
    spanRadius: '50%', //span按钮的圆角程度
    spanMargin: 3, //span之间的距离
})
    }
    window.addEventListener('DOMContentLoaded',tt)
</script>

```

## 视频

```
<div style="position: relative; width: 100%; height: 0; padding-bottom: 75%;">
    <iframe src="视频链接" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" allowfullscreen="true" style="position: absolute; width: 100%; height: 100%; left: 0; top: 0;"> </iframe>
</div>
```