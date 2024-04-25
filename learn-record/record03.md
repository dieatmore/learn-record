# 学习记录：Emmet 基本语法(一)

[TOC]

# 一、Emmet 语法简介

- Emmet (前身为 Zen Coding) 是一个能**大幅度提高前端开发效率的一个工具**。在前端开发的过程中，一大部分的工作是写 HTML、CSS 代码。特别是手动编写 HTML 代码的时候，效率会特别低下，因为需要敲打很多尖括号，而且很多标签都需要闭合标签等。于是，就有了 Emmet，它可以极大的提高代码编写的效率，它提供了一种非常简练的语法规则，然后立刻生成对应的 HTML 结构或者 CSS 代码，同时还有多种实用的功能帮助进行前端开发。
- VsCode 内置了 Emmet 语法,在后缀为.html/.css 中输入缩写后按 Tab 键即会自动生成相应代码

---

# 二、Emmet 常用语法总结

## 2.1 子元素： >

**tag1>tag2 表示在标签 tag1 内生成后代标签 tag2**

代码如下：
`div>ul>li` + tab 键

效果如下：

```html
<div>
  <ul>
    <li></li>
  </ul>
</div>
```

---

## 2.2 兄弟元素：+

**tag1+tag2 表示在标签 tag1 后生成兄弟标签 tag2**

代码如下：
`div+p` + tab 键

效果如下：

```html
<div></div>
<p></p>
```

---

## 2.3 上级元素：^

**tag1^tag2 表示在标签 tag1 的父级后生成兄弟标签 tag2，如果有两个^符号，则再提升一级(向上找父亲)，以此类推**

代码如下：
`div>span^p`

效果如下：

```html
<div><span></span></div>
<p></p>
```

多个父级代码案例：
`div>ul>li^^p`

效果如下：

```html
<div>
  <ul>
    <li></li>
  </ul>
</div>
<p></p>
```

---

## 2.4 分组元素：()

**使用操作符()即可将部分节点分组形成一个整体，将()内的节点与外面节点隔离，避免产生嵌套关系**

代码如下：
`div>(ul>li)+p`

效果如下：

```html
<div>
  <ul>
    <li></li>
  </ul>
  <p></p>
</div>
```

---

## 2.5 生成多个元素：\*

**tag1\*n 表示生成 n 个标签 tag1**

代码如下：
`ul>li*3`

效果如下：

```html
<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>
```

---

## 2.6 生成编号：$

**使用操作符$即可生成带有数字编号的标签属性值**

代码如下：
`ul>li.$*3`

效果如下：

```html
<ul>
  <li class="1"></li>
  <li class="2"></li>
  <li class="3"></li>
</ul>
```

> 注意：
>
> - `$`需搭配`*`使用，否则将会原样输出
> - `$`一般用在 id 名，类名，内容中
> - 当只有一个`$`时，数字从 1 开始,当有多个`$`时，数字从 0 开始

多个`$`代码如下:
`ul>li.item$$${666$}*3`

效果如下：

```html
<ul>
  <li class="item001">6661</li>
  <li class="item002">6662</li>
  <li class="item003">6663</li>
</ul>
```

---

## 2.7 随机填充：lorem

在编程中，使用 Lorem 来填充页面，用于**测试显示效果**。主要是通过编辑器中自带的 Emmet 插件，识别以 lorem 开头的短语，生成指定格式的内容

> 注意：lorem 短语需要手动输入，复制粘贴不会触发编辑器的

**用法：**

1. 新建默认数量词语的句子

   lorem + Tab/Enter，新建一共 30 个词语的句子

   > _效果如下：_
   > Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium molestiae recusandae asperiores. Velit omnis recusandae inventore a enim dignissimos? Dolore veritatis sequi asperiores aliquid facilis consequatur itaque odio alias illo.

2. 新建指定数量词语的句子

   loremN，其中 N 是一个数字，代表有 N 个词语(注意不是字符串长度为 N)
   代码：lorem10

   > _效果如下：_
   > Lorem ipsum dolor, sit amet consectetur adipisicing elit. Asperiores, amet!

3. 填充指定行数的内容

   lorem*N，其中 N 是一个数字代表有 N 行
   代码：lorem*3

   > _效果如下：_
   > Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt, laborum velit culpa, odio ex sit voluptas ipsam facilis et laboriosam unde blanditiis ipsa provident. Repellendus hic placeat perferendis veritatis enim.
   > Sapiente autem cumque eius praesentium velit, nihil nisi iusto officia quae harum, natus, veritatis architecto dignissimos pariatur amet? Libero unde doloribus doloremque autem nostrum laboriosam nulla assumenda aliquid officiis. Ullam.
   > Tempora explicabo soluta inventore aliquam nemo a minima. Obcaecati commodi omnis vel cumque! Voluptatibus dolores recusandae tempore perspiciatis temporibus velit cumque consectetur eius mollitia, eligendi ipsum tenetur laudantium animi distinctio.

4. 结合两者，填充指定行数且指定词语数量的内容

   loremN*M，填充 M 行内容，每行 N 个词语
   代码：lorem10*4

   > _效果如下：_
   > Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos, itaque.
   > Sunt delectus omnis vitae fugit nemo assumenda corporis vel mollitia?
   > Eius, hic. Aliquam tempore distinctio, nemo esse optio id dicta.
   > Deleniti modi maxime cupiditate nobis expedita nisi eaque veritatis recusandae.

5. 快速生成包含网页节点的内容

   案例代码：`p*4>lorem4`

   效果如下：

   ```html
   <p>Lorem ipsum dolor sit.</p>
   <p>Voluptates at corrupti voluptatem.</p>
   <p>Maiores dolorem minus necessitatibus?</p>
   <p>Iste natus architecto sint?</p>
   ```

---

# 三、总结

记录自己的学习过程，温故知新
