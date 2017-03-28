---
layout: post
title: 任务五：基础JavaScript练习（二）
category: javascript
---

## Lesson

* [任务五：基础JavaScript练习（二）](http://ife.baidu.com/course/detail/id/105)

## References

* [JavaScript入门篇](http://www.imooc.com/view/36)
* [MDN JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)

## Task

* [HTML & CSS preview](http://iymx.coding.me/ife/javascript/task05.html)
* [HTML & CSS source code](https://github.com/yangmaoxin/ife/blob/master/codes/javascript/task05.html)

**html**
```html
<input type="number" min="10" max="100" id="oInput">
<span id="btn_box">
    <button id="left_in">左侧入</button>
    <button id="right_in">右侧入</button>
    <button id="left_out">左侧出</button>
    <button id="right_out">右侧出</button>
    <button id="sort">冒泡排序</button>
    <button id="random">随机三十组数据</button>
</span>
<p>请输入10-100之间的数字</p>
<ul id="box"></ul>
```

**javascript**
```javascript
var box = document.getElementById("box"),
    oInput = document.getElementById("oInput"),
    btn_box = document.getElementById("btn_box"),
    timer,
    obj = box.children,
    btn = btn_box.children,
    moveNum=[0,0];

//给输入框添加监听事件
oInput.addEventListener('keyup', function() {
    if (/\D/g.test(oInput.value)) {
        alert('只能输入数字');
        oInput.value = '';
    };
    if (this.value >= 10 && this.value <= 100) {
        for(var i=0;i<btn.length;i++){
            btn[i].disabled = "";
        }
    } else {
        for(var i=0;i<btn.length;i++){
            btn[i].disabled = true;
        }
    }
});

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
        },1000);
        moveNum[0]++;
    }else if(name == "right_out"){
        obj[obj.length-moveNum[1]-1].setAttribute("class","moveOutR");
        setTimeout(function(){
            box.removeChild(box.lastElementChild);
            moveNum[1]--;
        },1000);
        moveNum[1]++;
    }
}       
    

//进入事件  
function moveIn(name,num){
    //如果num存在，则value＝num，否则值取输入框的值
    var val = num==undefined ? oInput.value : num; 
    // if(!val) {
    //     alert('请输入10-100之间的数字');
    //     return;
    // }
    if(obj.length>60){
    alert('数据已经超过60个，不能再增加了！！！');           
    }
    else{
        var oDiv = document.createElement("li"),
            text = document.createTextNode(val);
            oDiv.style.height = val*5+'px';
            oDiv.setAttribute('data-num',val);  //将输入的值存入data－num中
            oDiv.appendChild(text);
        if(name == "left_in"){
            oDiv.setAttribute("class","moveInL");
            box.insertBefore(oDiv,box.firstChild);
        }else if(name == "right_in"){
            oDiv.setAttribute("class","moveInR");
            box.appendChild(oDiv);
        }           
    }

}
//随机产生三十个数据，用于展示冒泡排序
function random(){
    box.innerHTML='';     //清空数据
    for(var i=0;i<30;i++) {
        if(i%2==0) {
            moveIn('left_in',parseInt(Math.random()*90+10));
        }
        else {
            moveIn('right_in',parseInt(Math.random()*90+10));
        }
    }
}

//改变两个节点位置
function change(num1,num2){
    obj[num1].className='RightMove';            //设置移动的动画
    obj[num2].className='LeftMove';
    setTimeout(function(){                      //在动画完成的瞬间将两个节点位置交换
        obj[num1].className='';                 //清空动画
        obj[num2].className='';
        box.insertBefore(obj[num2],obj[num1]);   //把小的（obj[num2]）移到大的前面(往左移)；
    },390);
}
//冒泡排序
function sort(){
    var i=obj.length,      //记录每次最后一组数据，即下次循环结束点
        j= 0,
        changeNum=0;   //记录每次交换时候的位置

    if(i==0) {
        alert('没有数据排序');
        return;
    }
    else if(i==1) {
        alert('只有一组数据，不需要排序');
        return;
    }
    timer=setInterval(function() {         //每隔500秒对比一组相邻数据
        if(j>=i-1) {
            j=0;
            if(!changeNum) {           //为0说明循环一次没有需要交换的，全部都满足了条件，故退出循环
                clearInterval(timer);
                timer=null;        //可以重新开始排序
                return 0;
            }
            i=changeNum;         //将这组最后一次交换的数据给i
            changeNum=0;                    //重新从第一个交换
        }
        setColor(j);      //设置颜色改变，便于观察
        //对比前后相邻的两组数据，如果前者比后者大就交换两个节点位置。
        if(obj[j].getAttribute('data-num') > obj[j+1].getAttribute('data-num')) {
            change(j,j+1);
            changeNum=j+1;      //重置交换的位置
        }
        j++;
    },500);
}
//设置颜色改变，便于观察
function setColor(j){
    obj[j].style.backgroundColor='blue';     //设置正在比较大小的节点颜色为blue
    obj[j+1].style.backgroundColor='blue';
    setTimeout(function(){
        obj[j].style.backgroundColor='red';      //清空之前设置的颜色
        obj[j+1].style.backgroundColor='red';
    },390);
}

//给按钮添加绑定事件
btn_box.addEventListener('click', function (e) {
    var event= e.target.id;
    //如果已经存在计时，则退出
    if(timer) {        
        alert('正在排序');
        return 0;
    }
    switch(event) {
        case 'left_in':
        case 'right_in':
            moveIn(event);
            break;
        case 'left_out':
        case 'right_out':
            moveOut(event);
            break;
        case 'sort':
            sort();
            break;
        case 'random':
            random();
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

<p data-height="265" data-theme-id="0" data-slug-hash="jBvQzJ" data-default-tab="result" data-user="y1m7x" data-embed-version="2" data-pen-title="js05" class="codepen">See the Pen <a href="http://codepen.io/y1m7x/pen/jBvQzJ/">js05</a> by y1m7x (<a href="http://codepen.io/y1m7x">@y1m7x</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

## Note

冒泡排序算法的运作如下：

比较相邻的元素。如果第一个比第二个大，就交换他们两个。

对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。在这一点，最后的元素应该会是最大的数。

针对所有的元素重复以上的步骤，除了最后一个。

持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。
