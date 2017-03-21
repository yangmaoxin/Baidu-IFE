---
layout: post
title: 任务一：零基础JavaScript编码（一）
category: javascript
---

## Lesson

* [任务一：零基础JavaScript编码（一）](http://ife.baidu.com/course/detail/id/93)

## References

* [JavaScript入门篇](http://www.imooc.com/view/36)
* [MDN JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)

## Task

* [HTML & CSS preview](http://iymx.coding.me/ife/javascript/task01/index.html)
* [HTML & CSS source code](https://github.com/yangmaoxin/ife/blob/master/codes/javascript/task01.html)

**html**
```
<label>请输入北京今天空气质量：<input id="aqi-input" type="text"></label>
<button id="button">确认填写</button>

<div>您输入的值是：<span id="aqi-display">尚无录入</span></div>
```

**javascript**
```
<script type="text/javascript">
(function() {
  /*  
  在注释下方写下代码
  给按钮button绑定一个点击事件
  在事件处理函数中
  获取aqi-input输入的值，并显示在aqi-display中
  */
  var $ = function (id) {
    return document.getElementById(id);
  }
  var handler = function (){
    var num = parseInt($("aqi-input").value);
    if((!isNaN(num)) && (num>=0) && (num<=1000)){
      $("aqi-display").innerHTML = num;
    } else {
      alert($("aqi-input").value + " 不是有效的AQI数值，请重新输入0-1000的有效整数！")
    }
  }
  $("button").onclick = function(){
    handler();
  }
  
  $("aqi-input").onkeyup = function (event) {
    if(event.keyCode === 13){
      handler();
    }
  }
  
})();
</script>
```

## Demo
<p data-height="265" data-theme-id="dark" data-slug-hash="xqYeqK" data-default-tab="result" data-user="ymx" data-embed-version="2" data-pen-title="js01" class="codepen">See the Pen <a href="http://codepen.io/ymx/pen/xqYeqK/">js01</a> by y1m7x (<a href="http://codepen.io/ymx">@ymx</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

## Note
用`$(id)`代替`document.getElementById(id)`
```
var $ = function (id) {
return document.getElementById(id);
}
```