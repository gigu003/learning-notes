---
title: HTML+CSS基础知识
date: '2023-10-05'
slug: html-css
categories:
- HTML+CSS笔记
tags:
- 浏览器
- 网页
- HTML标签
thumbnail: https://www.bleepstatic.com/content/hl-images/2021/05/26/Google___Chrome.jpg
---

## 浏览器

学习HTML和CSS肯定和浏览器密切相关，因为所有的HTML都需要有浏览器来渲染和观看。

目前主流的浏览器包括Chrome、Edge、Safari、Firefox、IE、Opera等等，也是目前比较主流的浏览器。

\> 浏览器内核是浏览器的核心，用于处理浏览器所得到的各种资源。

- Chrome： Blink内核
- Safari： webkit内核
- IE： Trident内核
- Firefox： Gecko内核
- Opera： Blink内核

目前IE浏览器已经停止更新和使用，我们在Windows系统上常见的Edge浏览器使用的是和Chrome一样的Blink内核。

## 网页

在浏览器地址栏中输入网址："www.chenq.site"，然后点击回车，我们把打开该地址看到的第一个页面称为**首页**，首页和其他通过网址打开的页面称之为**网页**，一个或多个网页构成了**网站**。

一个网页有哪些部分组成？一般认为网页要具备**结构+表现+行为**三个方面的要素，HTML构建网页的结构，CSS填充网页的表现、JS(JavaScript)构建网页的行为。


## HTML是什么

全称为：HpyerText Markup Language

翻译： **超文本**标记语言

超文本： 和普通文本比，内容更丰富。

标记： 文本要想变为超文本，需要用到各种标记符号。

语言： 每一个标记的写法、读音、使用规则，构成标记语言。



## HTML标签

> HTML通过使用标签来描述文档的结构和内容，这些标签由尖括号 \< 和 \> 包围，并且通常成对出现，包括开始标签和结束标签，例如 \<tagname\>内容\<\/tagname\>。

以下是一些常见的HTML标签及其用途：

- \<html\>：定义HTML文档的根元素。
- \<head\>：包含有关文档的元信息，如标题、字符集和链接到外部资源的标签。
- \<title\>：设置文档的标题，显示在浏览器标签页上。
- \<meta\>：提供关于文档的元信息，如字符集、作者和描述。
- \<link\>：用于链接外部资源，通常用于链接样式表（CSS）文件。
- \<script\>：用于包含JavaScript代码，可以放在文档的头部或主体部分。
- \<body\>：包含页面的主要内容，如文本、图片、链接和其他元素。
- \<h1\> - \<h6\>：定义标题，其中  \<h1\> 是最高级别的标题， \<h6\> 是最低级别的标题。
- \<p\>：定义段落。
- \<a\>：创建超链接，用于链接到其他页面或资源。
- \<img\>：插入图像。
- \<ul\>：创建无序列表。
- \<ol\>：创建有序列表。
- \<li\>：定义列表项。
- \<div\>：用于分组和样式化元素，常用于布局。
- \<span\>：用于在文本中应用样式或添加行内元素。
- \<table\>：创建表格。
- \<tr\>：定义表格的行。
- \<td\>：定义表格的数据单元格。
- \<th\>：定义表格的表头单元格。
- \<form\>：创建表单，用于用户输入。
- \<input\>：定义表单输入字段，如文本框、复选框和单选按钮。
- \<button\>：创建按钮。
- \<textarea\>：创建多行文本输入字段。
- \<select\>：创建下拉菜单。
- \<option\>：定义下拉菜单中的选项。
- \<label\>：为表单元素创建标签。
- \<iframe\>：嵌入其他网页或文档。
- \<audio\>：嵌入音频。
- \<video\>：嵌入视频。

这只是HTML标签的一小部分，还有许多其他标签用于不同的目的。HTML标签的组合和嵌套可以创建丰富的网页结构和内容。每个标签都有其自己的属性和用法，可以根据需要进行定制。\

标签又称为元素，是HTML的基本组成单位，标签分为双标签和单标签，标签名不区分大小写，但推荐小写，因为小写更规范。

双标签形式： \<标签名\> 内容\<\/标签名>

示例： \<marquee\> 学习代码更容易\<\/marquee\>

单标签形式： \<标签名\/\> \/可以省略。 示例：\<input\>

标签之间的关系：并列关系、嵌套关系、可以使用tab键进行缩进。

## 标签属性

> HTML标签可以具有各种属性，这些属性提供有关标签的额外信息或控制标签的行为。属性通常以名称-值对的形式出现，属性的名称在标签内部以等号 "=" 连接属性值。

以下是一些常见的HTML标签属性：

class: 用于为标签定义一个或多个类名，以便在CSS中选择和样式化这些元素。多个类名可以通过空格分隔。

```html
<div class="container">
内容
</div>
```
id: 为标签定义唯一的标识符。通常用于JavaScript中查找和操作元素。

```html
<div id="header">
内容
</div>
```

style: 用于为标签指定内联样式，直接应用于该元素。样式属性的值是CSS属性-值对。

```html
<p style="color: red; font-size: 16px;">这是红色文本</p>
```

src: 用于指定外部资源的URL，如图像的URL或脚本文件的URL。

```html
<img src="image.jpg" alt="图片">
```

placeholder: 用于为文本输入字段提供占位符文本，提示用户输入内容。

```html
<input type="text" placeholder="请输入您的姓名">
```
disabled: 用于禁用输入字段、按钮或其他交互元素，阻止用户进行交互。

```html
<button disabled>已禁用的按钮</button>
```
这只是一小部分常见的HTML属性。不同的HTML标签具有不同的属性，这些属性可以控制元素的外观、行为和功能。在使用属性时，请确保遵循HTML的语法规则和最佳实践。

- 标签属性用于给标签提供附加信息
- 可以写在起始标签中或单标签中
- 有些特殊的属性，没有属性名，只有属性值，例如\<input disabled\>

> 1. 不同的标签，有不同的属性；也有一些通用属性
> 1. 属性名、属性值不能乱写，都是W3C规定好的
> 1. 属性名、属性值都不区分大小写，但推荐小写
> 1. 双引号，也可以写成单引号，甚至不写都行，但还是推荐写双引号
> 1. 标签中不要出现同名属性，否则后写的会失效


## HTML基本结构

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>网页标题</title>
</head>
<body>
    <!-- 网页内容在这里 -->
</body>
</html>
```

这是一个基本的HTML结构，你可以在 \<body\> 部分添加各种HTML元素来构建网页的内容，如段落、图像、表格、链接等。根据需要，你可以在 \<head\> 部分添加更多的元信息和外部资源链接，如CSS样式表和JavaScript文件，以定制和增强你的网页。