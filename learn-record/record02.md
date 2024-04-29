# 学习记录：HTML 标签(一)

[TOC]

# 一、HTML 标签概述

## 1.1 HTML 标签简介

html 标签是指超文本标记语言的标记标签，html 标签是 html 语言中最基本的单位，html 标签是 html 最重要的组成部分。

---

## 1.2 HTML 标签特点

> HTML 标签的特点：
>
> - HTML 标签是由尖括号包围的关键词，比如 < html >
> - HTML 标签分别有双标签和单标签，标签中有属性，属性具有属性值。比如 < b> 和 < /b>为双标签，标签对中的第一个标签是开始标签，第二个标签是结束标签，开始和结束标签也被称为开放标签和闭合标签。
> - HTML 标签是与大小写无关的，例如“< BODY>”跟< body>表示的意思是一样的，推荐使用小写。

---

## 1.3 HTML 标签关系

​ 1. 父子关系(嵌套关系)

```html
<head>
  <title></title>
</head>
```

​ 2. 兄弟关系(并列关系)

```html
<head></head>
<body></body>
```

---

# 二、HTML 基本标签

## 2.1 `<div>`标签

- div 是 division 的简写，division 意为分割、区域、分组。比方说，当你将一系列的链接组合在一起，就形成了文档的一个 division。
- `<div>`可定义文档中的分区或节（division/section）。
- div 是一个[块级元素](https://so.csdn.net/so/search?spm=1010.2135.3001.4498&q=%E5%9D%97%E7%BA%A7%E5%85%83%E7%B4%A0&t=&u=)，可以包含段落，表格等内容，用于放置不同的内容。一般我们在网页**通过 div 来布局定位网页中的每个区块**。
- `<div>`可以把文档分割为独立的、不同的部分。它可以用作严格的组织工具，并且不使用任何格式与其关联。如果用 id 或 class 来标记 ，那么该标签的作用会变得更加有效。

---

## 2.2 `<span>`标签

- 在 html 中，span 标签是使用来组合文档中的[行内元素](https://so.csdn.net/so/search?spm=1010.2135.3001.4498&q=%E8%A1%8C%E5%86%85%E5%85%83%E7%B4%A0&t=&u=)，以便使用样式来对它们进行格式化。
- span 标签本身并没有什么格式表现（比如：换行等），需要对它应用样式才会有视觉上的变化。
- span 标签通常使用来将文本的一部分或者文档的一部分独立出来，从而**对独立的内容设置单独样式**。

案例代码如下：

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>html中span标签的详细介绍</title>
  </head>
  <body style="background-color: bisque;">
    <h3>span标签演示</h3>
    <p>
      html中
      <span style="color:blue;">span标签</span>
      的详细介绍
    </p>
  </body>
</html>
```

效果如下：

> <!DOCTYPE html><html>
>  <head>
>    <meta charset="utf-8" />
>    <title>html中span标签的详细介绍</title>
>  </head>
>  <body style="background-color: bisque;">
>    <h3>span标签演示</h3>
>    <p>html中<span style="color:blue;">span标签</span>的详细介绍
>    </p>
>  </body>
> </html>

---

## 2.3 `<div>`与`<span>`区别

由`<div>`与`<span>`引出块级元素与行内元素的区别
|块级元素|行内元素|
|:-:|:-:|
|块级元素始终从新行开始|行内元素从不从换行开始|
|块级元素从左到右覆盖空间|行内元素仅覆盖由 HTML 元素中的标记所限定的空间|
|块级元素具有上边距和下边距|行内元素没有上边距和下边距|

> - `<div>` 标签是一个**块级元素**。它用作 HTML 页面中的一个部分，用于对 HTML 元素的所有大部分进行分组。
> - `<span>`标签是一个**行内元素**。它用作突出显示或标记特定文本或文档部分的容器。

`<div>`与`<span>`对比代码如下：

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>span与div对比</title>
    <style type="text/css"></style>
  </head>
  <body>
    <h3>span与div对比</h3>
    测试
    <span>span"测试"一行显示</span>
    <div>div"测试"另起一行显示</div>
  </body>
</html>
```

效果如下：

> <!DOCTYPE html><html>
>  <head>
>    <meta charset="utf-8" />
>    <title>span与div对比</title>
>   <style type="text/css"></style>
>  </head>
>  <body>
>    <h3>span与div对比</h3>
>    测试<span>span"测试"一行显示</span><div>div"测试"另起一行显示</div>
>  </body>
> </html>

**总结`<span>`和`<div>`的区别在于**:

- `<div>`是一个**块级元素**，可以包含段落、标题、表格，乃至诸如章节、摘要和备注等。
- 而`<span>`是**行内元素**，`<span>`的前后是不会换行的，它没有结构的意义，纯粹是应用样式。

---

## 2.4 段落标签`<p>`

`<p>`标签非常简单，只需要在 HTML 文件中插入`<p>` `</p>`即可

代码如下：
`<p>这是一个段落</p>`

> `<p>`特点：
> 自动换行
> 段落和段落之间有空隙

案例代码如下：

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>古诗</title>
  </head>
  <body>
    <h3>锦瑟</h3>
    <p>锦瑟无端五十弦,一弦一柱思华年。</p>
    <p>庄生晓梦迷蝴蝶,望帝春心托杜鹃。</p>
    <p>沧海月明珠有泪,蓝田日暖玉生烟。</p>
    <p>此情可待成追忆,只是当时已惘然。</p>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>古诗</title>
    </head>
    <body>
        <h3>锦瑟</h3>
        <p>锦瑟无端五十弦,一弦一柱思华年。</p>
        <p>庄生晓梦迷蝴蝶,望帝春心托杜鹃。</p>
        <p>沧海月明珠有泪,蓝田日暖玉生烟。 </p>
        <p>此情可待成追忆,只是当时已惘然。</p>
    </body>
</html>

---

## 2.5 标题标签`<h>`

**h 标签通常用来表示创建一个标题**

> 注意：创建标题只有 `<h1>` ~ `<h6>`，没有其它的

从`<h1>`~`<h6>`**随数字增大，字体依次减小**

代码如下：

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
  </head>
  <body>
    <h1>标题1</h1>
    <h2>标题2</h2>
    <h3>标题3</h3>
    <h4>标题4</h4>
    <h5>标题5</h5>
    <h6>标题6</h6>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
</head>
<body>
    <h1>标题1</h1>
    <h2>标题2</h2>
    <h3>标题3</h3>
    <h4>标题4</h4>
    <h5>标题5</h5>
    <h6>标题6</h6>
</body>
</html>

---

## 2.6 换行标签`<br>`

br 是 break 的缩写，表示换行。
**`<br>` 是⼀个单标签 (不需要结束标签 )**
**<u>`<br/>`是规范写法</u>**，不建议写成`<br>`

> 注意：`<br>`标签只是简单地开始新的一行，跟段落不一样，所以不会产生段间距

案例代码如下：

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>古诗</title>
  </head>
  <body>
    <h3>锦瑟</h3>
    <br />
    锦瑟无端五十弦,一弦一柱思华年。
    <br />
    庄生晓梦迷蝴蝶,望帝春心托杜鹃。
    <br />
    沧海月明珠有泪,蓝田日暖玉生烟。
    <br />
    此情可待成追忆,只是当时已惘然。
  </body>
</html>
```

效果如下：

> <!DOCTYPE html>
> <html>
>    <head>
>        <meta charset="utf-8">
>        <title>古诗</title>
>    </head>
>    <body>
>        <h3>锦瑟</h3>
>        <br/>锦瑟无端五十弦,一弦一柱思华年。
>        <br/>庄生晓梦迷蝴蝶,望帝春心托杜鹃。
>        <br/>沧海月明珠有泪,蓝田日暖玉生烟。
>        <br/>此情可待成追忆,只是当时已惘然。
>    </body>
> </html>

而每一句用`<p>` `</p>`分割的代码效果如下：

> <!DOCTYPE html>
> <html>
>    <head>
>        <meta charset="utf-8">
>        <title>古诗</title>
>    </head>
>    <body>
>        <h3>锦瑟</h3>
>        <p>锦瑟无端五十弦,一弦一柱思华年。</p>
>        <p>庄生晓梦迷蝴蝶,望帝春心托杜鹃。</p>
>        <p>沧海月明珠有泪,蓝田日暖玉生烟。 </p>
>        <p>此情可待成追忆,只是当时已惘然。</p>
>    </body>
> </html>

对比可以清晰地看出`<br/>`没有`<p>` `</p>` 的段间距

---

## 2.7 分割线标签`<hr>`

`<hr>`标签非常简单，主要是在 html 中创建水平线

> **特点**：
>
> - hr 是单标签，是没有结束标签的
> - 水平是 100%的宽度，独立使用一行，并且上下内容有一定的距离

代码如下：

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>古诗</title>
  </head>
  <body>
    <hr />
    <hr />
    <hr />
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>古诗</title>
    </head>
    <body>
        <hr>
        <hr>
        <hr>
    </body>
</html>
<br/>
<br/>

---

## 2.8 表格标签`<table>`

`<table>`标签用来定义表格。每个表格均有若干行（由 <tr> 标签定义），每行被分割为若干单元格（由 <td> 标签定义）。字母 td 指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等
<br/>
**`<table>`的属性与用法：**
|表格|意义|
|:-:|:-:|
|`<table>`|定义表格|
|`<thead>`|定义表格的页眉|
|`<tbody>`|定义表格的主题|
|`<tfood>`|定义表格的页脚|
|`<th>`|定义表格的表头|
|`<tr>`|定义表格的行|
|`<td>`|定义表格的列|

**`<table>`**

1. **border**
   **用于设置表格边框的宽度**
   不加 border 属性代码如下:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>table</title>
  </head>
  <body>
    <table>
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
      <tr>
        <td>二行一列</td>
        <td>二行二列</td>
        <td>二行三列</td>
      </tr>
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
    </table>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>table</title>
</head>
<body>
	<table>
        <tr>
            <td>一行一列</td>
            <td>一行二列</td>
            <td>一行三列</td>
        </tr>
        <tr>
             <td>二行一列</td>
             <td>二行二列</td>
             <td>二行三列</td>
        </tr>
        <tr>
             <td>一行一列</td>
             <td>一行二列</td>
             <td>一行三列</td>
        </tr>
    </table>
</body>
</html>

添加 border 属性代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>table</title>
  </head>
  <body>
    <table border="1">
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
      <tr>
        <td>二行一列</td>
        <td>二行二列</td>
        <td>二行三列</td>
      </tr>
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
    </table>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>table</title>
</head>
<body>
	<table border="1">
        <tr>
            <td>一行一列</td>
            <td>一行二列</td>
            <td>一行三列</td>
        </tr>
        <tr>
             <td>二行一列</td>
             <td>二行二列</td>
             <td>二行三列</td>
        </tr>
        <tr>
             <td>一行一列</td>
             <td>一行二列</td>
             <td>一行三列</td>
        </tr>
    </table>
</body>
</html>

2. **width 和 height**
   **用来设置表格的宽度与长度(可以使用像素和百分比两种方式)**

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>table</title>
  </head>
  <body>
    <table border="1" width="100" height="80%">
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
      <tr>
        <td>二行一列</td>
        <td>二行二列</td>
        <td>二行三列</td>
      </tr>
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
    </table>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>table</title>
</head>
<body>
	<table border="1" width="100" height="80%">
        <tr>
            <td>一行一列</td>
            <td>一行二列</td>
            <td>一行三列</td>
        </tr>
        <tr>
             <td>二行一列</td>
             <td>二行二列</td>
             <td>二行三列</td>
        </tr>
        <tr>
             <td>一行一列</td>
             <td>一行二列</td>
             <td>一行三列</td>
        </tr>
    </table>
</body>
</html>

3. **align**
   **设置表格的对齐方式，属性值有 left(左对齐(默认))、center(居中)、right(右对齐)三种**

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>table</title>
  </head>
  <body>
    <table border="1" width="100" height="60" align="right">
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
      <tr>
        <td>二行一列</td>
        <td>二行二列</td>
        <td>二行三列</td>
      </tr>
      <tr>
        <td>一行一列</td>
        <td>一行二列</td>
        <td>一行三列</td>
      </tr>
    </table>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>table</title>
</head>
<body>
	<table border="1" width="100" height="60" align="right">
        <tr>
            <td>一行一列</td>
            <td>一行二列</td>
            <td>一行三列</td>
        </tr>
        <tr>
             <td>二行一列</td>
             <td>二行二列</td>
             <td>二行三列</td>
        </tr>
        <tr>
             <td>一行一列</td>
             <td>一行二列</td>
             <td>一行三列</td>
        </tr>
    </table>
</body>
</html>

4. **cellspacing 和 cellpadding**
   > - **cellspacing:规定单元格之间的空白。(单位：px;)**
   > - **cellpadding:规定单元边沿与其内容之间的空白。(单位：px；)**

> 注意：当 cellspacing 的值等于 0 时，就和我们平时看见的表格一样

5. **`<thead>`、`<tbody>`、`<tfoot>`、`<caption>`和`<th>`**
   > - `<thead>`:定义表格的页眉
   > - `<tbody>`:定义表格的主题
   > - `<tfoot>`:定义表格的页脚
   > - `<caption>`:定义表格标题
   > - `<th>`:定义表格的表头(文字会加粗并居中)

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>table</title>
  </head>
  <body>
    <table width="80" height="100" align="center" border="1" cellspacing="0" celladding="1">
      <caption>学生成绩表</caption>
      <thead>
        <tr>
          <th>姓名</th>
          <th>成绩</th>
        </tr>
      </thead>
      <tfoot>
        <tr>
          <td>总和</td>
          <td>190</td>
        </tr>
      </tfoot>
      <tbody>
        <tr>
          <td>张三</td>
          <td>97</td>
        </tr>
        <tr>
          <td>李四</td>
          <td>93</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>table</title>
  </head>
  <body>
    <table width="80" height="100" align="center" border="1" cellspacing="0" celladding="1">
      <caption>学生成绩表</caption>
      <thead>
        <tr>
          <th>姓名</th>
          <th>成绩</th>
        </tr>
      </thead>
      <tfoot>
        <tr>
          <td>总和</td>
          <td>190</td>
        </tr>
      </tfoot>
      <tbody>
        <tr>
          <td>张三</td>
          <td>97</td>
        </tr>
        <tr>
          <td>李四</td>
          <td>93</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>

6. **`<tr>`和`<td>`**

   > - **tr：定义表格的行**
   > - **td:定义表格单元**

7. **rowspan 和 colspan**
   > - **rowspan:规定单元格可横跨的行数**
   > - **colspan:规定单元格可横跨的列数**

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>table</title>
  </head>
  <body>
    <table width="100" height="70" align="center" border="1" cellspacing="0">
      <caption>关于rowspan和colspan的表</caption>
      <tbody>
        <tr>
          <td rowspan="2"></td>
          <td colspan="2"></td>
          <td></td>
        </tr>
        <tr>
          <td></td>
          <td colspan="2"></td>
        </tr>
        <tr>
          <td colspan="2"></td>
          <td></td>
          <td></td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>table</title>
  </head>
  <body>
    <table width="300" height="70" align="center" border="1" cellspacing="0">
      <caption>关于rowspan和colspan的表</caption>
      <tbody>
        <tr>
          <td rowspan="2"></td>
          <td colspan="2"></td>
          <td></td>
        </tr>
        <tr>
          <td></td>
          <td colspan="2"></td>
        </tr>
        <tr>
          <td colspan="2"></td>
          <td></td>
          <td></td>
        </tr>
      </tbody>
    </table>
  </body>
</html>

---

`<table>`练习:
![练习](https://github.com/dieatmore/learn-record/assets/162850821/b7c79cda-a1fc-4f88-bd3b-daa1d8c8f79c)

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>作业1</title>
  </head>
  <body>
    <h1>工商银行电子汇款单</h1>
    <table border="1" cellspacing="0">
      <thead>
        <tr>
          <th width="100" colspan="2">回单类型</th>
          <th width="500">网上转账</th>
          <th width="100" colspan="2">指令序号</th>
          <th width="500">213254135454</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td rowspan="4" width="30">收款人</td>
          <td width="70">户名</td>
          <td width="500">张三</td>
          <td rowspan="4" width="30">付款人</td>
          <td width="70">户名</td>
          <td width="500">老刘</td>
        </tr>
        <tr>
          <td width="70">卡号</td>
          <td width="500">0000000001</td>
          <td width="70">卡号</td>
          <td width="500">0000000002</td>
        </tr>
        <tr>
          <td width="70">地区</td>
          <td width="500">南京</td>
          <td width="70">地区</td>
          <td width="500">杭州</td>
        </tr>
        <tr>
          <td width="70">网点</td>
          <td width="500">工商江苏南京业务处理中心</td>
          <td width="70">网点</td>
          <td width="500">江苏徐州业务中心</td>
        </tr>
        <tr>
          <td colspan="2" width="100">币种</td>
          <td width="500">人民币</td>
          <td colspan="2" width="50">钞汇标志</td>
          <td width="500">钞票</td>
        </tr>
        <tr>
          <td colspan="2" width="100">金额</td>
          <td width="500">1.00元</td>
          <td colspan="2" width="50">手续费</td>
          <td width="500">0.75元</td>
        </tr>
        <tr>
          <td colspan="2" width="100">合计</td>
          <td width="1100" colspan="4">人民币(大写):壹</td>
        </tr>
        <tr>
          <td colspan="2" width="100">交易时间</td>
          <td width="500">2017年6月01号</td>
          <td colspan="2" width="100">时间截止</td>
          <td width="500">2017-06-01-13:00.00.00000</td>
        </tr>
      </tbody>
    </table>
    <p>票据打印时间：2017-06-01 15：00：12</p>
    <p><del>票据打印单位：江苏徐州业务中心</del></p>
    <p>操作员：大营</p>
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>作业1</title>
</head>
<body>
	<h1>工商银行电子汇款单</h1>
	<table border="1" cellspacing="0">
	<thead>
		<tr>
				<th width="100" colspan="2">回单类型</th>
				<th width="500">网上转账</th>
				<th width="100" colspan="2">指令序号</th>
				<th width="500">213254135454</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td rowspan="4" width="30">收款人</td>
			<td width="70">户名</td>
			<td width="500">张三</td>
			<td rowspan="4" width="30">付款人</td>
			<td width="70">户名</td>
			<td width="500">老刘</td>
		</tr>
		<tr>
			<td width="70">卡号</td>
			<td width="500">0000000001</td>
			<td width="70">卡号</td>
			<td width="500">0000000002</td>
		</tr>
		<tr>
			<td width="70">地区</td>
			<td width="500">南京</td>
			<td width="70">地区</td>
			<td width="500">杭州</td>
		</tr>
		<tr>
			<td width="70">网点</td>
			<td width="500">工商江苏南京业务处理中心</td>
			<td width="70">网点</td>
			<td width="500">江苏徐州业务中心</td>
		</tr>
		<tr>
			<td colspan="2" width="100">币种</td>
			<td width="500">人民币</td>
			<td colspan="2" width="50">钞汇标志</td>
			<td width="500">钞票</td>
		</tr>
		<tr>
			<td colspan="2" width="100">金额</td>
			<td width="500">1.00元</td>
			<td colspan="2" width="50">手续费</td>
			<td width="500">0.75元</td>
		</tr>
		<tr>
			<td colspan="2" width="100">合计</td>
			<td width="1100" colspan="4">人民币(大写):壹</td>
		</tr>
		<tr>
			<td colspan="2" width="100">交易时间</td>
			<td width="500">2017年6月01号</td>
			<td colspan="2" width="100">时间截止</td>
			<td width="500">2017-06-01-13:00.00.00000</td>
		</tr>
	</tbody>
	</table>
	<p>票据打印时间：2017-06-01 15：00：12</p>
	<p><del>票据打印单位：江苏徐州业务中心</del></p>
	<p>操作员：大营</p>
</body>
</html>

---

## 2.9 无序列表标签`<ul>`和`<li>`

无序列表是没有刻意顺序的列表,比如我们如果想去超市买东西，想买的东西又比较多，为了避免忘记漏买某些东西，就会列一个购物清单，购物清单就是一个无序列表，因为要买的东西只要没有遗漏就好，不需要给它排列顺序
**无序列表使用`<ul>` `</ul>`标签，每个列表项都是`<li>` `</li>`标签**

> 注意：
>
> - `<ul>`标签和`<li>`标签是紧密相关的，`<ul>`标签的字标签只能是`<li>`
> - `<li>`标签不能单独使用,`<li>`必须放到无序列表标签`<ul>`或者有序列表标签`<ol>`中
> - `<li>`标签中可以放其他任何标签

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>作业1</title>
  </head>
  <body>
    <h1>购物清单</h1>
    <ul>
      <li>面包</li>
      <li>
        牛奶
        <p>脱脂或者低脂</p>
      </li>
      <li>鸡蛋</li>
      <li>咖啡</li>
      <li>水果</li>
    </ul>
  </body>
</html>
```

效果如下：

<!DOCTYPE html><html lang="en">
  <head>
	<meta charset="UTF-8">
	<title>作业1</title>
  </head>
  <body>
    <h1>购物清单</h1>
    <ul>
      <li>面包</li>
      <li>牛奶
        <p>脱脂或者低脂</p>
      </li>
      <li>鸡蛋</li>
    <li>咖啡</li>
    <li>水果</li>
    </ul>
  </body>
</html>

## 2.10 图像标签`<img>`

`<img>`元素向网页中嵌入一幅图像。
`<img>`标签有两个必需的属性：**src 属性** 和 **alt 属性**

> 注意：在 HTML 中，`<img>`标签没有结束标签

1. **`<img>`标签的 src 属性**

`<img>`标签的 src 属性是必需的。它的值是图像文件的 URL，也就是引用该图像的文件的的[绝对路径](https://so.csdn.net/so/search?spm=1010.2135.3001.4498&q=%E7%BB%9D%E5%AF%B9%E8%B7%AF%E5%BE%84&t=&u=)或[相对路径](https://so.csdn.net/so/search?q=%E7%9B%B8%E5%AF%B9%E8%B7%AF%E5%BE%84&t=&u=&urw=)。

2. **`<img>`标签的 alt 属性**

alt 属性是一个必需的属性，**它规定在图像无法显示时的替代文本**

alt 的好处就是，假设网速太慢，图片路径错误，用户无法查看图片，alt 属性就可以为图像提供替代的文字信息。

代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>图片标签</title>
  </head>
  <body>
    <img src="C:\workspace-csdn\learn-record\image.png" alt="工商银行电子汇款单" />
  </body>
</html>
```

效果如下：

<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <title>图片标签</title>
    </head>
    <body>
        <img src="C:\workspace-csdn\learn-record\image.png"  alt="工商银行电子汇款单" />
    </body>
</html>

# 三、总结

记录自己的学习过程，温故知新
