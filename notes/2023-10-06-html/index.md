---
title: "HTML基础知识"
author: "陈琼"
date: '2023-10-06'
slug: html
categories:
  - HTML+CSS笔记
tags:
  - HTML注释
  - 文档声明
  - 字符编码
image: 'https://cdn.jsdelivr.net/gh/gigu003/db/images/html.png'
draft: false
---
## HTML注释

**特点**：注释的内容会被浏览器所忽略，不会呈现到页面中，但源代码中依然可见。

**作用**：对代码进行解释和说明。

**写法**：

```html
<!-- 下面的文字只能滚动一次 -->
<marquee loop="1">滚动的文字</marquee>

<!-- 下面的文字可以无限滚动 -->
<marquee loop="1">滚动的文字</marquee>
```

> 注释不可以嵌套

**快捷键**：

CTRL + \/

## HTML文档声明

声明网页类型为HTML5，目前绝大部分网页类型为HTML5。

```html
<!DOCTYPE html>
```

## 字符编码

ASCII ：大号字母、小写字母、数字、一些符号，共计128个。

ISO 8859-1 ：在ASCII 基础上，扩充了一些希腊字符等，共计是256个。

GB2312：继续扩充，收录了 6763 个常用汉字、682个字符。

GBR ：收录了的汉宇和符号达到 20000+，支持繁体中文。

UTE-8：万国码，包含世界上所有语言的：所有文字与符号。 —— 很常用。

> - 原则1：储存时，务必采用合适的字符编码，否则无法储存，数据会丢失！
> - 原则2：储存时采用哪种方式编码，读取时就必须采用相同方式解码。否则数据能呈现，但数据错乱（乱码）！

指定方法：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title><HTML字符编码</title>
</head>
<body>
  
</body>
</html>
```

## 语言

```html
<html lang="en">
```

## HTML标准结构

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
  
</body>
</html>
```
