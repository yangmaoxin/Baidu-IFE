---
layout: post
title: 任务一：零基础HTML编码
category: html&css
---

## Lesson

* [任务一：零基础HTML编码](http://ife.baidu.com/course/detail/id/90)

## References

* [Web 建站技术中，HTML、HTML5、XHTML、CSS、SQL、JavaScript、PHP、ASP.NET、Web Services 是什么？](https://www.zhihu.com/question/22689579)
* [MDN HTML 入门](https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/Introduction)
* [SemanticUI Theming Examples](http://semantic-ui.com/examples/theming.html)

## Demo

* [example page](/example)

## Task

* [HTML Tags preview](http://iymx.coding.me/ife/html/task01/index.html)
* [HTML Tags source code](https://github.com/discountry/my-baidu-ife/blob/master/codes/html&css/1-html-tags.html)

**html**

```html
 <!--标题导航区域-->
  <header>
        <nav>
      <h1>网站一级标题</h1>
      <ul>
        <li><a href="#">导航链接一</a></li>
        <li><a href="#">导航链接二</a></li>
        <li><a href="#">导航链接三</a></li>
        <li><a href="#">导航链接四</a></li>    
      </ul>
    </nav>
  </header>
  <main>
    <article>
      <h2>文章一级标题</h2>
      <h2>文章二级标题</h2>
      <p>文章作者 文章发表时间</p>
      <p>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，<br/>换行了<br/>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，换行了<br/>这是一个很长很长的段落，这是一个很长很长的段落，<a href = "http://ife.baidu.com">这里有个链接链接到http://ife.baidu.com</a>这是一个很长很长的段落，<strong>这里有个粗体字</strong>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落。</p>
      <img src="task.png">
      <p>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，<br/>换行了<br/>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，换行了<br/>这是一个很长很长的段落，这是一个很长很长的段落，<a href = "http://ife.baidu.com" target="_blank">这里有个链接点击后打开新窗口链接到http://ife.baidu.com</a>这是一个很长很长的段落，<strong>这里有个粗体字</strong>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落。</p>
    </article>
    <article>
      <h2>另一篇文章一级标题</h2>
      <h2>文章二级标题</h2>
      <p>文章作者 文章发表时间</p>
      <p>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，<br/>换行了<br/>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落，换行了<br/>这是一个很长很长的段落，这是一个很长很长的段落，<a href = "http://ife.baidu.com">这里有个链接链接到http://ife.baidu.com</a>这是一个很长很长的段落，<strong>这里有个粗体字</strong>这是一个很长很长的段落，这是一个很长很长的段落，这是一个很长很长的段落。</p>
      <img src="task.png">
      <ul>
        <li>列表项目一</li>
        <li>列表项目二</li>
        <li>列表项目三</li>
      </ul>
    </article>


      <article>
    <h2>图片</h2>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    <figure>
        <figcaption>好看的图片</figcaption>
        <img src="task.png">
    </figure>
    
    </article>

 <!--表单-->
      <article>
    <h2>最后一篇文章一级标题</h2>
    <h2>文章二级标题</h2>
    <p>文章作者 文章发表时间</p>
    <ol>
      <li>排名1</li>
      <li>排名2</li>
      <li>排名3</li>
    </ol>
    <p>下面是一个表格，给表格加了一个border="1"好让你看出是一个表格</p>
    <table border="1">
      <tr>
        <th>表头</th>
        <th>表头</th>
        <th>表头</th>
      </tr>
      <tr>
        <td>表内容单元格</td>
        <td>表内容单元格</td>
        <td><a href="#">操作</a></td>
      </tr>

      <tr>
        <td>表内容单元格</td>
        <td>表内容单元格</td>
        <td><a href="#">操作</a></td>
      </tr>

      <tr>
        <td>表内容单元格</td>
        <td>表内容单元格</td>
        <td><a href="#">操作</a></td>
      </tr>

      <tr>
        <td>表内容单元格</td>
        <td>表内容单元格</td>
        <td><a href="#">操作</a></td>
      </tr>

      <tr>
        <td>总计</td>
        <td colspan="2">1000</td>
      </tr>
    </table>
    <aside>
    <h2>这里以后是一个侧栏，这是侧栏的标题</h2>
    <h2>侧栏注册窗口标题</h2>
    <form>
    <p><span>请输入邮箱地址：</span><input type="text" placeholder="这是一个文本输入框"></p>
    <p>邮箱地址请按要求格式输入</p>
    <p><span>请输入密码：</span><input type="password" placeholder="这是一个文本输入框"><span>请重复输入密码：</span><input type="password" placeholder="这是一个文本输入框"></p>
    <p>密码请为6-16位英文数字</p>

    <label>性别：</label>
    <input type="radio" name="sex" value="male" id="male" checked><label for="male">男</label> 
    <input type="radio" name="sex" value="female" id="female"><label for="female">女</label> 
    <label>城市：</label>
    <select name="city">   
          <option value="1">北京</option>   
          <option value="2">武汉</option>   
          <option value="3">长沙</option>   
          <option value="4">汕头</option>   
          <option value="5">广州</option>      
      </select>  

    <label>爱好</label>
        <label><input type="checkbox" name="hobby" value="sport">运动</label>
        <label><input type="checkbox" name="hobby" value="art">艺术</label>
        <label><input type="checkbox" name="hobby" value="science">科学</label>

      <label>个人描述：</label>
      <textarea>这是一个多行输入框，输入您的个人描述</textarea>
      <input type="submit" value="确认提交">
    </form>
    </aside>
    </article>
  </main>

    <footer>版权所有©</footer>
```

## Note

* [HTML Character](https://www.w3.org/TR/2011/WD-html5-20110113/named-character-references.html)
* [MDN HTML element reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

