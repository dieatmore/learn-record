# 学习记录：CSS 基础(一)

[TOC]

# 一、CSS 概述

## 1.1 什么是 CSS？

CSS 是“Cascading Style Sheet”的缩写，中文意思为“**层叠样式表**”（层层叠加的样式），它是一种标准的**样式表语言**，用于描述网页的表现形式（例如网页元素的位置、大小、颜色等）。

CSS 的**主要作用是定义网页的样式**（美化网页），对网页中元素的位置、字体、颜色、背景等属性进行精确控制。CSS 不仅可以静态地修饰网页，还可以配合 JavaScript 动态地修改网页中元素的样式，而且市面上几乎所有的浏览器都支持 CSS。

## 1.2 CSS 优点

- 将 HTML 文档的表现与内容分离
- 使 HTML 文档结构简化/清晰/灵活
- 极大的提高了 HTML 文档的可读性
- [Cascading](https://so.csdn.net/so/search?q=Cascading&t=&u=&urw=)使样式结构简化/清晰/灵活
- 增强了网站全局的一致性
- CSS 文件存储在浏览器的高速缓存中，多个页面不必重新装载分析样式，降低网络数据传输
- 便于针对不同设备目标定制不同的样式

## 1.3 CSS 特点

- 丰富的样式定义
- 易于使用和修改
- 多页面应用
- 层叠
- 页面压缩

---

# 二、CSS 语法规范

**选择器 + 若干属性声明**

如图：
![image](https://github.com/dieatmore/learn-record/assets/162850821/a9089360-3313-4a59-8837-9dfa476c9206)


> **注意：不要在属性值与单位之间留有空格！**

如下图：
错误方法(有空格)：
![image](https://github.com/dieatmore/learn-record/assets/162850821/e0175e00-d57a-4490-8a5b-ad0d7a2f5af5)


正确方法(无空格)：
![image](https://github.com/dieatmore/learn-record/assets/162850821/1ba4d665-51d7-422d-9611-a2accc779836)


---

# 三、CSS 选择器

## 3.1 元素选择器

**元素选择器基于元素名称(类型)，选择所有相同元素**

代码如下：

```HTML
<style>
      p {
        color: blue;
      }
</style>
```

```html
<p>Lorem ipsum dolor sit.</p>
<p>Cupiditate, impedit? Est, tenetur.</p>
<p>Dolores ratione enim placeat.</p>
```

效果如下(**影响页面所有 p 元素**)：
![image](https://github.com/dieatmore/learn-record/assets/162850821/3a4ca156-c20c-4731-b71e-bf12877cd932)


## 3.2 id 选择器

**ID 选择器基于 HTML 元素的 ID 属性来选择特定的元素**

- 使用`#id名`，定义 id 选择器
- 元素 id 应在一个页面内具有唯一性
- ID 名称不能以数字开头

代码如下：

```html
<style>
  #para1 {
    color: aqua;
  }
</style>
```

```html
<p id="para1">Lorem ipsum dolor sit.</p>
<p>Cupiditate, impedit? Est, tenetur.</p>
<p>Dolores ratione enim placeat.</p>
```

效果如下(**仅影响 id 为 para1 的元素**)：
![image](https://github.com/dieatmore/learn-record/assets/162850821/e1d0b22f-da76-4876-9a12-9625095f04e9)


> 注意：Id=para1 的 p 元素样式由 p 选择器，以及 id 选择器**层叠**决定

## 3.3 class 选择器

**class 选择器基于 HTML 元素 class 属性值，选择一组特定的元素**

- 使用`.class名`，定义 class 选择器
- 定义一类样式，可针对不同类型元素

代码如下：

```html
<style>
  .center {
    text-align: center;
  }
</style>
```

```html
<p class="center">Cupiditate, impedit? Est, tenetur.</p>
<div class="center">Dolores ratione enim placeat.</div>
<h3 class="center">Lorem ipsum dolor sit.</h3>
```

效果如下(**不同类型元素可以引用相同的 class**)：
![image](https://github.com/dieatmore/learn-record/assets/162850821/95b99f07-4caf-497e-93bb-de9fbdbea501)


---

> **可以指定只有特定的元素受 class 的影响 (元素.类名)**

代码如下：

```html
<style>
  h3.center {
    text-align: center;
  }
</style>
```

效果如下(指定 h3)：
![image](https://github.com/dieatmore/learn-record/assets/162850821/e4ed3a29-ffd3-4000-b649-214e2dd6ad5c)


---

> **一个元素可以同时引用多个 class**

代码如下：

```html
<style>
  .center {
    text-align: center;
  }
  .red {
    color: crimson;
  }
</style>
```

```html
<p class="center">Cupiditate, impedit? Est, tenetur.</p>
<div class="center">Dolores ratione enim placeat.</div>
<h3 class="center red">Lorem ipsum dolor sit.</h3>
```

效果如下：
