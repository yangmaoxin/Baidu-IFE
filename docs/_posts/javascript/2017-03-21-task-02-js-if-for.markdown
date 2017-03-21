---
layout: post
title: 任务二：零基础JavaScript编码（二）
category: javascript
---

## Lesson

* [任务二：零基础JavaScript编码（二）](http://ife.baidu.com/course/detail/id/93)

## References

* [JavaScript入门篇](http://www.imooc.com/view/36)
* [MDN JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)

## Task

* [HTML & CSS preview](http://iymx.coding.me/ife/javascript/task02.html)
* [HTML & CSS source code](https://github.com/yangmaoxin/ife/blob/master/codes/javascript/task02.html)

**html**
```html
  <h3>污染城市列表</h3>
  <ul id="aqi-list">
<!--   
    <li>第一名：福州（样例），10</li>
      <li>第二名：福州（样例），10</li> -->
  </ul>
```

**javascript**
```javascript
<script type="text/javascript">
var aqiData = [
  ["北京", 90],
  ["上海", 50],
  ["福州", 10],
  ["广州", 50],
  ["成都", 90],
  ["西安", 100]
];
(function () {
  /*
  在注释下方编写代码
  遍历读取aqiData中各个城市的数据
  将空气质量指数大于60的城市显示到aqi-list的列表中
  */
  aqiData.sort(function(a, b) {
    return b[1] - a[1];
  });
  var aqiNode = document.getElementById('aqi-list');
  for (var i = 0; i < aqiData.length; i++) {
    if (aqiData[i][1] > 60) {
      aqiNode.innerHTML = aqiNode.innerHTML + '<li>' + '第' + (i+1) + '名:' + aqiData[i][0] + ',' + aqiData[i][1] + '</li>';
    }
  }
})();
</script>
```

## Demo
<p data-height="265" data-theme-id="dark" data-slug-hash="yMvmYE" data-default-tab="js,result" data-user="ymx" data-embed-version="2" data-pen-title="js02" class="codepen">See the Pen <a href="http://codepen.io/ymx/pen/yMvmYE/">js02</a> by y1m7x (<a href="http://codepen.io/ymx">@ymx</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>