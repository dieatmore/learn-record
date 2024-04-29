# 学习记录：Emmet 基本语法(二)

[TOC]

# 一、Emmet 常用语法

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

## 1.2 属性 []

**tag1[属性] 表示在标签 tag1 内生成属性**

代码如下：
`div[name=syz age=18]`

效果如下：

```html
<div name="syz" age="18"></div>
```

---

## 1.3 id

**使用 # 生成带有 id 名字的标签**

代码如下：
`div#header`

效果如下：

```html
<div id="header"></div>
```

---

## 1.4 class .

**使用 . 生成带有类名的标签**

代码如下：
`div.page`

效果如下：

```html
<div class="page"></div>
```

---

## 1.5 文本内容 {}

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

# 二、Emmet 详情

## 2.1 了解更多 Emmet 网址

- **[Emmet 使用详解](https://blog.csdn.net/comphoner/article/details/79670148)**

- **[Emmet 使用手册](http://www.360doc.com/content/16/0317/23/30381994_543197175.shtml)**

---

## 2.2 Emmet 官网

**[Emmet 缩写语法 官网速查表](https://docs.emmet.io/cheat-sheet/)**

**[Emmet 官网说明文档](https://docs.emmet.io/abbreviations/syntax/)**

---

# 三、总结

记录自己的学习过程，温故知新
