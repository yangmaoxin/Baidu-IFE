---
layout: post
title: 任务四：基础JavaScript练习（一）
category: javascript
---

## Lesson

* [任务四：基础JavaScript练习（一）](http://ife.baidu.com/course/detail/id/103)

## References

* [JavaScript入门篇](http://www.imooc.com/view/36)
* [MDN JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)

## Task

* [HTML & CSS preview](http://iymx.coding.me/ife/javascript/task04.html)
* [HTML & CSS source code](https://github.com/yangmaoxin/ife/blob/master/codes/javascript/task04.html)

**html**
```html
<input type="text" id="oInput">
<span id="btn_box">
    <button id="left_in">左侧入</button>
    <button id="right_in">右侧入</button>
    <button id="left_out">左侧出</button>
    <button id="right_out">右侧出</button>
</span>
<div id="box"></div>
```

**javascript**
```javascript
  var box = document.getElementById("box"),
    oInput = document.getElementById("oInput"),
    btn_box = document.getElementById("btn_box"),
    obj = box.children,
    moveNum=[0,0];
    
  //移出事件  
  function moveOut(name){
    if(obj.length == 0){
      alert("数据为空，不能再移出");
      return;
    }
      /*
       * moveNum处理，当连续多次点击按钮时，会无法找到对应节点
       *
       * moveNum［0］＝ n 记录左侧有多少正在处于离开的节点，但是还没有被移除节点
       * moveNum［1］＝ n 记录右侧有多少正在处于离开的节点，但是还没有被移除节点
       * 下一次再点击动画时，处理的是子节点的第n个
       * */   
    if(name == "left_out"){
      obj[moveNum[0]].className="moveOutL";   
      setTimeout(function(){
        box.removeChild(box.firstElementChild);
        moveNum[0]--;
      },2000);
      moveNum[0]++;
    }else if(name == "right_out"){
      obj[obj.length-moveNum[1]-1].setAttribute("class","moveOutR");
      setTimeout(function(){
        box.removeChild(box.lastElementChild);
        moveNum[1]--;
      },2000);
      moveNum[1]++;
    }
  }   
    

  //进入事件  
  function moveIn(name){
    var val = oInput.value;
      if(!val || parseInt(val)>100 || parseInt(val)<0 || /[^0-9]/.test(val)) {
          alert('请输入0-100之间的数字');
          return;
      }
      var oDiv = document.createElement("div"),
        text = document.createTextNode(val);
        oDiv.appendChild(text);
    if(name == "left_in"){
      oDiv.setAttribute("class","moveInL");
      box.insertBefore(oDiv,box.firstChild);
    }else if(name == "right_in"){
      oDiv.setAttribute("class","moveInR");
      box.appendChild(oDiv);
    }
  }
  //给按钮添加绑定事件
  btn_box.addEventListener('click', function (e) {
      var event= e.target.id;
      switch(event) {
          case 'left_in':
          case 'right_in':
              moveIn(event);
              break;
          case 'left_out':
          case 'right_out':
              moveOut(event);
              break;
      }
  })
  //点击队列中任何一个元素，则该元素会被从队列中删除
  box.addEventListener('click', function (e) {
      var target = e.target;
      if(target.className) {
          setTimeout(function () {
              box.removeChild(target);
          }, 1000);
      }
  })
```

## Demo

<p data-height="265" data-theme-id="dark" data-slug-hash="XMqeKr" data-default-tab="result" data-user="y1m7x" data-embed-version="2" data-pen-title="js04" class="codepen">See the Pen <a href="http://codepen.io/y1m7x/pen/XMqeKr/">js04</a> by y1m7x (<a href="http://codepen.io/y1m7x">@y1m7x</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

## Note

