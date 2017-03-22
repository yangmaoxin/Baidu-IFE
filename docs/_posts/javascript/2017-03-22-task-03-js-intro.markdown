---
layout: post
title: 任务三：零基础JavaScript编码（三）
category: javascript
---

## Lesson

* [任务三：零基础JavaScript编码（三）](http://ife.baidu.com/course/detail/id/98)

## References

* [JavaScript入门篇](http://www.imooc.com/view/36)
* [MDN JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)

## Task

* [HTML & CSS preview](http://iymx.coding.me/ife/javascript/task03.html)
* [HTML & CSS source code](https://github.com/yangmaoxin/ife/blob/master/codes/javascript/task03.html)

**html**
```html
<ul id="source">
  <li>北京空气质量：<b>90</b></li>
  <li>上海空气质量：<b>70</b></li>
  <li>天津空气质量：<b>80</b></li>
  <li>广州空气质量：<b>50</b></li>
  <li>深圳空气质量：<b>40</b></li>
  <li>福州空气质量：<b>32</b></li>
  <li>成都空气质量：<b>90</b></li>
</ul>
<ul id="resort">
</ul>
<button id="sort-btn">排序</button>
```

**javascript**
```javascript
<script type="text/javascript">
/**
 * getData方法
 * 读取id为source的列表，获取其中城市名字及城市对应的空气质量
 * 返回一个数组，格式见函数中示例
 */
function getData() {
  /*
  coding here
  */

  /*
  data = [
    ["北京", 90],
    ["北京", 90]
    ……
  ]
  */
  var data = [];
  var source = document.getElementById('source').children;
  var sourceLength = source.length;

  for(var i = 0; i < sourceLength; i++) {
    //data.push(source[i].innerText);
    //data[i] = data[i].split("：");
    //使用正则表达式RegExp相关的方法来来读取和处理字符数据
    var ret = /(\S+)空气质量：<b>(\d+)/.exec(source[i].innerHTML);
    console.log(ret);
    data.push(new Array(
      ret[1],
      parseInt(ret[2])
    ));
  }
  return data;

}
/**
 * sortAqiData
 * 按空气质量对data进行从小到大的排序
 * 返回一个排序后的数组
 */
function sortAqiData(data) {
  data.sort(function(a, b) {
    return a[1] - b[1];
  })
  return data;
}

/**
 * render
 * 将排好序的城市及空气质量指数，输出显示到id位resort的列表中
 * 格式见ul中的注释的部分
 */
function render(data) {
  var resort = "";
  var chineseNumbers = ["一", "二", "三", "四", "五", "六", "七", "八", "九", "十"];
  for(var i = 0; i < data.length; i++) {
    resort += "<li>第" + chineseNumbers[i] + "名：" + data[i][0] + "空气质量：" + "<b>" + data[i][1] + "</b>" + "</li>";
  }
  document.getElementById("resort").innerHTML = resort;
}

function btnHandle() {
  var aqiData = getData();
  aqiData = sortAqiData(aqiData);
  render(aqiData);
}

function init() {

  // 在这下面给sort-btn绑定一个点击事件，点击时触发btnHandle函数
  //document.getElementById('sort-btn').onclick = function() {
  //  btnHandle();
  //}
  //  IE9+及其它浏览器支持addEventListener方式注册事件处理程序
  document.getElementById("sort-btn").addEventListener("click", btnHandle);
}

init();
</script>
```

## Demo

<p data-height="265" data-theme-id="dark" data-slug-hash="WpzJvE" data-default-tab="result" data-user="ymx" data-embed-version="2" data-pen-title="js03" class="codepen">See the Pen <a href="http://codepen.io/ymx/pen/WpzJvE/">js03</a> by y1m7x (<a href="http://codepen.io/ymx">@ymx</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

## Note

* [RegExp.prototype.exec()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec)