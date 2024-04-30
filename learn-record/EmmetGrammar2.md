# 学习记录：Emmet 基本语法(二)

[TOC]

# 一、本文概述

本文延续了[学习记录：Emmet 基本语法(一)](https://blog.csdn.net/di_213/article/details/138203605?spm=1001.2014.3001.5501)，继续扩展了 Emmet 语法的知识，能力有限，若想了解更多 Emmet 语法，可参考以下网址：

> - **[Emmet 使用手册](http://www.360doc.com/content/16/0317/23/30381994_543197175.shtml)**

---

# 二、Emmet 常用语法

## 1.1 自动生成 HTML 模板

`!` + `Tab`可以快速生成完整结构的 HTML 代码

效果如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

---

## 1.2 属性 `[]`

**tag1[属性] 表示在标签 tag1 内生成属性**

代码如下：
`div[name=syz age=18]`

效果如下：

```html
<div name="syz" age="18"></div>
```

---

## 1.3 id `#`

**使用 # 生成带有 id 名字的标签**

代码如下：
`div#header`

效果如下：

```html
<div id="header"></div>
```

---

## 1.4 class `.`

**使用 . 生成带有类名的标签**

代码如下：
`div.page`

效果如下：

```html
<div class="page"></div>
```

---

## 1.5 文本内容 `{}`

**在生成的标签内部写内容可以用{ }**

代码如下：
`div{这是一个片段}`

效果如下：

```html
<div>这是一个片段</div>
```

---

## 1.6 快速生成 CSS 样式语法

**大部分属性直接输入属性名的简写形式即可**

- 同时设置宽高
  代码如下：
  `w200+h200`

  效果如下：

  ```html
  width: 200px; height: 200px;
  ```

- 设置行高
  代码如下：
  `lh26px`

  效果如下：

  ```html
  line-height: 26px;
  ```

- 设置背景色
  代码如下：
  `bgc:#bababa`

  效果如下：

  ```html
  background-color: #bababa;
  ```

还有很多可以快速生成的属性：

1. 输入`fwb`即可生成代码片段`font-weight: bold；`
2. 输入`m10`即可生成代码片段 m`argin: 10px；`
3. 输入`df`即可生成代码片段`display: flex；`
4. 输入`jcc`即可生成代码片段`justify-content: center；`
5. 输入`aic`即可生成代码片段`align-items: center；`
6. 输入`poa`即可生成代码片段`position: absolute；`
7. 输入`tac`即可生成代码片段`text-align: center；`
   ……

根据上面的例子，其实可以发现规律，**Emmet 中用首字母+具体值的形式生成 CSS 代码片段**，这里就不全部列举了，读者可以在编辑器中自行尝试

---

## 1.7 隐式标签

1. `body`下` div`内部直接写`.class`或`#class`默认转换结果为`<div id="class"></div>`
2. `p` `h1~h5` `a` `span` `p`标签等文本标签内部写`.class`或`#class`默认转换结果为`<span class="class"></span>`
3. `ul` 内部默认转换为 `li`
4. `table`一级默认为`tr`二级默认为`td`

---

# 三、Emmet 官网

**[Emmet 缩写语法 官网速查表](https://docs.emmet.io/cheat-sheet/)**

**[Emmet 官网说明文档](https://docs.emmet.io/abbreviations/syntax/)**

---

# 四、语法及标签缩写详细方法

后代：`>`
缩写：`nav>ul>li`

```html
<nav>
  <ul>
    <li></li>
  </ul>
</nav>
```

兄弟：`+`
缩写：`div+p+bq`

```html
<div></div>
<p></p>
<blockquote></blockquote>
```

上级：`^`
缩写：`div+div>p>span+em^bq`

```html
<div></div>
<div>
  <p>
    <span></span>
    <em></em>
  </p>
  <blockquote></blockquote>
</div>
```

缩写：`div+div>p>span+em^^bq`

```html
<div></div>
<div>
  <p>
    <span></span>
    <em></em>
  </p>
</div>
<blockquote></blockquote>
```

分组：`()`
缩写：`div>(header>ul>li*2>a)+footer>p`

```html
<div>
  <header>
    <ul>
      <li><a href=""></a></li>
      <li><a href=""></a></li>
    </ul>
  </header>
  <footer><p></p></footer>
</div>
```

缩写：`(div>dl>(dt+dd)*3)+footer>p`

```html
<div>
  <dl>
    <dt></dt>
    <dd></dd>
    <dt></dt>
    <dd></dd>
    <dt></dt>
    <dd></dd>
  </dl>
</div>
<footer><p></p></footer>
```

乘法：`*`
缩写：`ul>li*5`

```html
<ul>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ul>
```

自增符号：`$`
缩写：`ul>li.item$*5`

```html
<ul>
  <li class="item1"></li>
  <li class="item2"></li>
  <li class="item3"></li>
  <li class="item4"></li>
  <li class="item5"></li>
</ul>
```

缩写：`h$[title=item$]{Header $}*3`

```html
<h1 title="item1">Header 1</h1>
<h2 title="item2">Header 2</h2>
<h3 title="item3">Header 3</h3>
```

缩写：`ul>li.item$$$*5`

```html
<ul>
  <li class="item001"></li>
  <li class="item002"></li>
  <li class="item003"></li>
  <li class="item004"></li>
  <li class="item005"></li>
</ul>
```

缩写：`ul>li.item$@-*5`

```html
<ul>
  <li class="item5"></li>
  <li class="item4"></li>
  <li class="item3"></li>
  <li class="item2"></li>
  <li class="item1"></li>
</ul>
```

缩写：`ul>li.item$@3*5`

```html
<ul>
  <li class="item3"></li>
  <li class="item4"></li>
  <li class="item5"></li>
  <li class="item6"></li>
  <li class="item7"></li>
</ul>
```

ID 和类属性
缩写：`#header`

```html
<div id="header"></div>
```

缩写：`.title`

```html
<div class="title"></div>
```

缩写：`form#search.wide`

```html
<form id="search" class="wide"></form>
```

缩写：`p.class1.class2.class3`

```html
<p class="class1 class2 class3"></p>
```

自定义属性
缩写：`p[title="Hello world"]`

```html
<p title="Hello world"></p>
```

缩写：`td[rowspan=2 colspan=3 title]`

```html
<td rowspan="2" colspan="3" title=""></td>
```

缩写：`[a='value1' b="value2"]`

```html
<div a="value1" b="value2"></div>
```

文本：`{}`
缩写：`a{Click me}`

```html
<a href="">Click me</a>
```

缩写：`p>{Click }+a{here}+{ to continue}`

```html
<p>
  Click
  <a href="">here</a>
  to continue
</p>
```

隐式标签
缩写：`.class`

```html
<div class="class"></div>
```

缩写：`em>.class`

```html
<em><span class="class"></span></em>
```

缩写：`ul>.class`

```html
<ul>
  <li class="class"></li>
</ul>
```

缩写：`table>.row>.col`

```html
<table>
  <tr class="row"><td class="col"></td></tr>
</table>
```

HTML
所有未知的缩写都会转换成标签，例如，`foo → <foo></foo>`

缩写：`!`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

缩写：`a`

```html
<a href=""></a>
```

缩写：`a:link`

```html
<a href="http://"></a>
```

缩写：`a:mail`

```html
<a href="mailto:"></a>
```

缩写：`abbr`

```html
<abbr title=""></abbr>
```

缩写：`acronym`

```html
<acronym title=""></acronym>
```

缩写：`base`

```html
<base href="" />
```

缩写：`basefont`

```html
<basefont />
```

缩写：`br`

```html
<br />
```

缩写：`frame`

```html
<frame />
```

缩写：`hr`

```html
<hr />
```

缩写：`bdo`

```html
<bdo dir=""></bdo>
```

缩写：`bdo:r`

```html
<bdo dir="rtl"></bdo>
```

缩写：`bdo:l`

```html
<bdo dir="ltr"></bdo>
```

缩写：`col`

```html
<col />
```

缩写：`link`

```html
<link rel="stylesheet" href="" />
```

缩写：`link:css`

```html
<link rel="stylesheet" href="style.css" />
```

缩写：`link:print`

```html
<link rel="stylesheet" href="print.css" media="print" />
```

缩写：`link:favicon`

```html
<link rel="shortcut icon" type="image/x-icon" href="favicon.ico" />
```

缩写：`link:touch`

```html
<link rel="apple-touch-icon" href="favicon.png" />
```

缩写：`link:rss`

```html
<link rel="alternate" type="application/rss+xml" title="RSS" href="rss.xml" />
```

缩写：`link:atom`

````html
<link rel="alternate" type="application/atom+xml" title="Atom" href="atom.xml" />
` 缩写：`meta` ```html
<meta />
````

缩写：`meta:utf`

```html
<meta http-equiv="Content-Type" content="text/html;charset=UTF-8" />
```

缩写：`meta:win`

```html
<meta http-equiv="Content-Type" content="text/html;charset=windows-1251" />
```

缩写：`meta:vp`

```html
<meta
  name="viewport"
  content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0" />
```

缩写：`meta:compat`

```html
<meta http-equiv="X-UA-Compatible" content="IE=7" />
```

缩写：`style`

```html
<style></style>
```

缩写：`script`

```html
<script></script>
```

缩写：`script:src`

```html
<script src=""></script>
```

缩写：`img`

```html
<img src="" alt="" />
```

缩写：`iframe`

```html
<iframe src="" frameborder="0"></iframe>
```

缩写：`embed`

```html
<embed src="" type="" />
```

缩写：`object`

```html
<object data="" type=""></object>
```

缩写：`param`

```html
<param name="" value="" />
```

缩写：`map`

```html
<map name=""></map>
```

缩写：`area`

```html
<area shape="" coords="" href="" alt="" />
```

缩写：`area:d`

```html
<area shape="default" href="" alt="" />
```

缩写：`area:c`

```html
<area shape="circle" coords="" href="" alt="" />
```

缩写：`area:r`

```html
<area shape="rect" coords="" href="" alt="" />
```

缩写：`area:p`

```html
<area shape="poly" coords="" href="" alt="" />
```

缩写：`form`

```html
<form action=""></form>
```

缩写：`form:get`

```html
<form action="" method="get"></form>
```

缩写：`form:post`

```html
<form action="" method="post"></form>
```

缩写：`label`

```html
<label for=""></label>
```

缩写：`input`

```html
<input type="text" />
```

缩写：`inp`

```html
<input type="text" name="" id="" />
```

缩写：`input:hidden`

别名：`input[type=hidden name]`

```html
<input type="hidden" name="" />
```

缩写：`input:h`

别名：`input:hidden`

```html
<input type="hidden" name="" />
```

缩写：`input:text, input:t`

别名：`inp`

```html
<input type="text" name="" id="" />
```

缩写：`input:search`

别名：`inp[type=search]`

```html
<input type="search" name="" id="" />
```

缩写：`input:email`

别名：`inp[type=email]`

```html
<input type="email" name="" id="" />
```

缩写：`input:url`

别名：`inp[type=url]`

```html
<input type="url" name="" id="" />
```

缩写：`input:password`

别名：`inp[type=password]`

```html
<input type="password" name="" id="" />
```

缩写：`input:p`

别名：`input:password`

```html
<input type="password" name="" id="" />
```

缩写：`input:datetime`

别名：`inp[type=datetime]`

```html
<input type="datetime" name="" id="" />
```

缩写：`input:date`

别名：`inp[type=date]`

```html
<input type="date" name="" id="" />
```

缩写：`input:datetime-local`

别名：`inp[type=datetime-local]`

```html
<input type="datetime-local" name="" id="" />
```

缩写：`input:month`

别名：`inp[type=month]`

```html
<input type="month" name="" id="" />
```

缩写：`input:week`

别名：`inp[type=week]`

```html
<input type="week" name="" id="" />
```

缩写：`input:time`

别名：`inp[type=time]`

```html
<input type="time" name="" id="" />
```

缩写：`input:number`

别名：`inp[type=number]`

```html
<input type="number" name="" id="" />
```

缩写：`input:color`

别名：`inp[type=color]`

```html
<input type="color" name="" id="" />
```

缩写：`input:checkbox`

别名：`inp[type=checkbox]`

```html
<input type="checkbox" name="" id="" />
```

缩写：`input:c`

别名：`input:checkbox`

```html
<input type="checkbox" name="" id="" />
```

缩写：`input:radio`

别名：`inp[type=radio]`

```html
<input type="radio" name="" id="" />
```

缩写：`input:r`

别名：`input:radio`

```html
<input type="radio" name="" id="" />
```

缩写：`input:range`

别名：`inp[type=range]`

```html
<input type="range" name="" id="" />
```

缩写：`input:file`

别名：`inp[type=file]`

```html
<input type="file" name="" id="" />
```

缩写：`input:f`

别名：`input:file`

```html
<input type="file" name="" id="" />
```

缩写：`input:submit`

```html
<input type="submit" value="" />
```

缩写：`input:s`

别名：`input:submit`

```html
<input type="submit" value="" />
```

缩写：`input:image`

```html
<input type="image" src="" alt="" />
```

缩写：`input:i`

别名：`input:image`

```html
<input type="image" src="" alt="" />
```

缩写：`input:button`

```html
<input type="button" value="" />
```

缩写：`input:b`

别名：`input:button`

```html
<input type="button" value="" />
```

缩写：`isindex`

```html
<isindex />
```

缩写：`input:reset`

别名：`input:button[type=reset]`

```html
<input type="reset" value="" />
```

缩写：`select`

```html
<select name="" id=""></select>
```

缩写：`option`

```html
<option value=""></option>
```

缩写：`textarea`

```html
<textarea name="" id="" cols="30" rows="10"></textarea>
```

缩写：`menu:context`

别名：`menu[type=context]>`

```html
<menu type="context"></menu>
```

缩写：`menu:c`

别名：`menu:context`

```html
<menu type="context"></menu>
```

缩写：`menu:toolbar`

别名：`menu[type=toolbar]>`

```html
<menu type="toolbar"></menu>
```

缩写：`menu:t`

别名：`menu:toolbar`

```html
<menu type="toolbar"></menu>
```

缩写：`video`

```html
<video src=""></video>
```

缩写：`audio`

```html
<audio src=""></audio>
```

缩写：`html:xml`

```html
<html xmlns="http://www.w3.org/1999/xhtml"></html>
```

缩写：`keygen`

```html
<keygen />
```

缩写：`command`

```html
<command />
```

缩写：`bq`

别名：`blockquote`

```html
<blockquote></blockquote>
```

缩写：`acr`

别名：`acronym`

```hrml
<acronym title=""></acronym>
```

缩写：`fig`

别名：`figure`

```html
<figure></figure>
```

缩写：`figc`

别名：`figcaption`

```html
<figcaption></figcaption>
```

缩写：`ifr`

别名：`iframe`

```html
<iframe src="" frameborder="0"></iframe>
```

缩写：`emb`

别名：`embed`

```html
<embed src="" type="" />
```

缩写：`obj`

别名：`object`

```html
<object data="" type=""></object>
```

缩写：`src`

别名：`source`

```html
<source></source>
```

缩写：`cap`

别名：`caption`

```html
<caption></caption>
```

缩写：`colg`

别名：`colgroup`

```html
<colgroup></colgroup>
```

缩写：`fst, fset`

别名：`fieldset`

```html
<fieldset></fieldset>
```

缩写：`btn`

别名：`button`

```html
<button></button>
```

缩写：`btn:b`

别名：`button[type=button]`

```html
<button type="button"></button>
```

缩写：`btn:r`

别名：`button[type=reset]`

```html
<button type="reset"></button>
```

缩写：`btn:s`

别名：`button[type=submit]`

```html
<button type="submit"></button>
```

# 五、总结

记录自己的学习过程，温故知新
