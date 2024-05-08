# 学习记录：CSS Units&Box Model

[TOC]

# 一、长度单位 Units

## 1.1 Units 概述

Units 是 CSS 单位，CSS 有几种不同的单位来表示长度，许多 CSS 属性采用“长度”值，如宽度、边距、填充、字体大小、边框宽度等。对于某些 CSS 属性，**允许使用负长度**

**长度单位有两种类型:**

- 相对长度单位
- 绝对长度单位

---

## 1.2 相对长度单位

**相对长度单位指定相对于另一个长度特性的长度**。相对长度单位在不同渲染介质之间的缩放效果更好。
|单位| 描述|
|:-:|:-:|
|em| 相对于当前字体的字体大小(2em 表示当前字体大小的 2 倍)|
|ex| 相对于当前字体的 X 高度(很少使用)|
|ch| 相对于数字“ 0 ”的宽度|
|rem| 相对于根元素的字体大小|
|vw| 相对于视口宽度的 1%_|
|vh| 相对于视口高度的 1%_|
|vmin| 相对于视口*较小尺寸的 1%|
|vmax| 相对于视口*较大尺寸的 1%|
|%||

---

### 1.2.1 em

**em，相对于当前元素应有尺寸的倍数**

代码如下：

```html
<style>
  #px1 {
    font-size: 16px;
    line-height: 2px;
  }
  #px2 {
    font-size: 30px;
    border: 1px solid black;
  }
  #em1 {
    font-size: 0.5em;
    color: blue;
  }
</style>
```

```html
<p id="px1">Lorem ipsum dolor sit amet, consectetur adipisicing</p>
<div id="px2">
  Lorem ipsum dolor sit amet consectetur adipisicing elit.
  <span id="em1">Lorem ipsum dolor sit amet consectetur.</span>
  Lorem, ipsum dolor sit amet consectetur adipisicing elit.
</div>
```


效果如下：

<img width="776" alt="3d01e17061edd2d9ad436122cf44d65" src="https://github.com/dieatmore/learn-record/assets/162850821/a80d26a4-a113-48ef-8600-436438433a2e">

> div 内字体为 30px，span 的 em 则相对于 30px 的 0.5 倍,最终字体为 15px

**应用场景：首行缩进，使用相对单位，与字体 px 尺寸无关**

首行缩进代码如下：

```html
<style>
  #indent {
    text-indent: 2em;
  }
</style>
```

```html
<p id="indent">
  首行缩进两字符，与字体尺寸无关
  <br />
  首行缩进两字符，与字体尺寸无关
</p>
```

首行缩进效果如下：

<img width="214" alt="c80c1ae895fabe6b0173dadb2ac77e9" src="https://github.com/dieatmore/learn-record/assets/162850821/552db646-9c0d-40d2-9723-a07717222678">


---

### 1.2.2 rem

**rem 相对于根，即 html 元素设置的尺寸，在没有显式声明时。浏览器默认 html 字体为 16px**

代码如下：

```html
<style>
  #rem1 {
    font-size: 30px;
    border: 1px solid #000;
  }
  #rem2 {
    font-size: 0.5rem;
  }
</style>
```

```html
<div id="rem1">
  The font-size of div is 30px
  <span id="rem2">The font-size of span is 16px*0.5=8px</span>
</div>
```

效果如下：

<img width="776" alt="86541184166e19efed4c3db56f4f205" src="https://github.com/dieatmore/learn-record/assets/162850821/974c53dc-cff9-41fd-975c-74fb044a3d9b">


> **rem 相对于 html 设置，而非当前尺寸**

---

### 1.2.3 %

**%，相对于父容器设置的百分比**

代码如下：

```html
<style>
  #father {
    width: 80%;
    font-size: 30px;
    border: 1px solid #000;
  }
  #son {
    width: 50%;
    font-size: 80%;
    border: 1px solid #000;
  }
</style>
```

```html
<div id="father">
  father
  <div id="son">son</div>
</div>
```

效果如下：

<img width="629" alt="19b432c5c204b156297cd0672b863b5" src="https://github.com/dieatmore/learn-record/assets/162850821/8c639431-9611-4598-b611-7b514bf191d6">


> - father 为当前宽度的 80%
> - son 为 father 宽度的 50%
> - son 的 font-size 为 Father 的 80%

## 1.3 绝对长度单位

**绝对长度单位是固定的，用其中任何一种单位表示的长度都将精确地显示为该大小**
像素(CSS Pixel)，像素长度和你在显示器上看到的文 字屏幕像素无关，实际上是一个按角度度量的单位，CSS 样式中的逻辑像素
|单位 |说明|
|:-:|:-:|
|cm| 厘米|
|mm| 毫米|
|in| 英寸(1in=96px=2.54cm)|
|px| 像素(1px=1 英寸的 1/96)|
|pt| 点数(1pt=1 英寸的 1/72)|
|pc|派卡(1pc=12pt)|

- CSS 像素，是一个相对(具体物理设备)的绝对单位
- 即在同一设备上，1px 长度是相同的，但在不同设备上，1px 长度是不同的

---

# 二、盒子模型 Box Model

## 2.1 Box Model 概述

**所有 HTML 元素都可以被视为盒子**。在 CSS 中，当谈论设计和布局时，使用术语“box model”。box model 本质上是一个包装每个 HTML 元素的盒子。

**box model 包括:**

- 外边距. 清除边框外的区域，外边距是透明的。
- 边框. 围绕在内边距和内容外的边框。
- 内边距. 清除内容周围的区域，内边距是透明的。
- 内容. 盒子的内容，显示文本和图像。

盒子模型如图所示：

<img width="720" alt="image" src="https://github.com/dieatmore/learn-record/assets/162850821/9085095a-d995-4240-8416-57258c11e6a3">


---

## 2.2 边框 Borders

CSS 边框属性允许您指定元素边框的样式、宽度和颜色。

- 边框样式
- 边框宽度
- 边框颜色
- 边界半径
- 边界-单独的边
- 边框速记属性

### 2.2.1 边框样式

**边框样式，指定要显示的边框类型**

<img width="752" alt="7987a79587d2c91ebe6ec60a2f86fd1" src="https://github.com/dieatmore/learn-record/assets/162850821/57fc96b0-29b3-48b7-b4ad-51b4d4a52af6">


---

### 2.2.2 边框宽度

**边框宽度 border-width，指定四个边框的宽度**。
border-width 属性可以有一到四个值（上边框、右边框、下边框和左边框）。边框宽度支持按上下左右分别声明，单位支持 px em， 以及预定义的 thin, medium, or thick 值

---

### 2.2.3 边框速记属性

**为了缩短代码，还可以在一个属性中指定所有单独的边框属性**
border 属性是以下各个边框属性的简写属性:
边框宽度
边框样式(必需)
边框颜色

代码如下：

```html
p { border: 5px solid red; }
```

此属性是 border-width、border-style 和 border-color 的简写属性。

---

### 2.2.4 border-radius

**border-radius 属性用于向元素添加圆形边框**

代码如下：

```html
<style>
  p.normal {
    border: 1px solid red;
  }
  p.round1 {
    border: 1px solid red;
    border-radius: 5px;
  }
  p.round2 {
    border: 1px solid red;
    border-radius: 8px;
  }
  p.round3 {
    border: 1px solid red;
    border-radius: 12px;
  }
</style>
```

```html
<p class="normal">normal border</p>
<p class="round1">round border</p>
<p class="round2">rounder border</p>
<p class="round3">roundest border</p>
```

效果如下：

<img width="777" alt="0243df5a0fb13ba251d7f0bc531906c" src="https://github.com/dieatmore/learn-record/assets/162850821/c0ebb755-dd72-411a-9365-b67153e3fc1a">


---

## 2.3 内边距 Padding

**Padding，内边距，决定了内容至边线的距离**

- CSS 填充属性用于在内容周围生成空间。
- 填充将清除元素内容周围的区域（边框内）。
- 有一些 CSS 属性用于设置元素每一侧（顶部、右侧、底部和左侧）的填充。
- **填充是透明的**
- CSS 具有指定元素每一侧填充的属性：padding-top；padding-right；padding-bottom；padding-left

Padding 示例代码如下：

```html
<style>
  div.padding {
    background-color: lightblue;
    border: 1px solid #000;
    padding-top: 50px;
    padding-right: 10px;
    padding-bottom: 50px;
    padding-left: 100px;
  }
</style>
```

```html
<div class="padding">
  Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore itaque harum impedit. Quo nisi,
  cumque animi, molestiae saepe libero nostrum quidem ad perferendis fugiat explicabo, quia maiores
  inventore ipsa placeat laborum assumenda.
</div>
```

效果如下：

<img width="779" alt="b0c25b567cef2605c6b520225c2a46e" src="https://github.com/dieatmore/learn-record/assets/162850821/ccb84121-b4a7-43d9-9337-17d148619b4d">


---

### 2.3.1 内边距速记属性

**要缩短代码，可以在一个属性中指定所有内边距属性。**

`padding: 25px 50px 75px 100px;`

- top padding is 25px
- right padding is 50px
- bottom padding is 75px
- left padding is 100px
  > 简写为 4 项：上，右，下，左

---

`padding: 25px 50px 75px;`

- top padding is 25px
- right and left paddings are 50px
- bottom padding is 75px
  > 简写为 3 项：上，左右，下

---

`padding: 25px 50px;`

- top and bottom paddings are 25px
- right and left paddings are 50px
  > 简写为 2 项：上下，左右

---

`padding: 25px;`

- all four paddings are 25px
  > 简写为 1 项：上下左右

## 2.4 外边距 Margin

**CSS 外边距属性用于在元素周围生成空间。**

- 边缘是透明的。
- 边距属性设置边框外空白的大小。
- 外边距速记属性与内边距相同
- 空间颜色不由元素本身决定，而由父容器决定

Margin 示例代码如下：

```html
<style>
  div.margin {
    border: 1px solid #000;
    margin: 100px 150px 100px 80px;
    background-color: lightblue;
  }
</style>
```

```html
<div class="margin">
  Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore itaque harum impedit. Quo nisi,
  cumque animi, molestiae saepe libero nostrum quidem ad perferendis fugiat explicabo, quia maiores
  inventore ipsa placeat laborum assumenda.
</div>
```

效果如下：

<img width="781" alt="bff26bc3145688cd1ce642095bac181" src="https://github.com/dieatmore/learn-record/assets/162850821/a5270d0d-3748-499f-8161-56fe482e481d">


> - 元素内容至其他元素距离由内、外边距共同决定
> - 元素本身可以定义 Padding 区域颜色,但无法定义 Margin 区域颜色

### 2.4.1 auto

**“自动”值。您可以将 margin 属性设置为 auto，以使元素在其容器内水平居中.(必须指定宽度)，然后，该元素将占用指定的宽度，剩余的空间将在左右边距之间平均分配**

auto 示例代码如下：

```html
<style>
  div.center {
    border: 1px solid red;
    width: 300px;
    margin: auto;
  }
</style>
```

```html
<div>
  Lorem ipsum dolor sit, amet consectetur adipisicing elit. Labore itaque harum impedit. Quo nisi,
  cumque animi, molestiae saepe libero nostrum quidem ad perferendis fugiat explicabo, quia maiores
  inventore ipsa placeat laborum assumenda.
</div>
<div class="center">Lorem ipsum dolor sit amet consectetur adipisicing elit. Minus, inventore.</div>
```

效果如下：

<img width="781" alt="e979d20c4f77b4f9e418e7eba93066d" src="https://github.com/dieatmore/learn-record/assets/162850821/aa43c179-156f-499e-a9d1-af7301a7006e">


> 当指定了宽度，且设置 margin 为 auto 时可实现元素随窗口尺寸动态变化始终水平居中

> **注意：width 必须在 margin 前设置**

---

### 2.4.2 外边距塌陷(Margin Collapse)

外边距塌陷：**元素的顶部边距和底部边距有时会折叠为单个边距，该边距等于两个边距中的最大值。**

示例代码如下：

```html
<style>
  h1 {
    margin: 0 0 50px 0;
  }
  h2 {
    margin: 20px 0 0 0;
  }
</style>
```

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
```

效果如下(h1 与 h2 之间的 Margin 取最大值，50px)：

<img width="170" alt="09d8e6f2c45a94796b762520f3485d7" src="https://github.com/dieatmore/learn-record/assets/162850821/05c1c0b1-0f97-435a-9380-ace668dac4dc">


> **元素垂直方向的 margin 会`坍塌`为 2 元素最大的 margin 值而非 2 元素 margin 之和**

---

# 三、总结

记录自己的学习过程，温故知新
