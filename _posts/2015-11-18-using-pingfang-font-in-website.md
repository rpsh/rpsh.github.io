---
layout: post
title: "在网页上使用苹方字体"
description: "在网页上使用苹方字体。通过 CSS 定义网页中文字体为苹方： CSS font-family: PingFangSC-Regular。苹方提供了六个字种，简、繁、繁（港）三类，使用方法如文"
keyword: "苹方, 苹方字体, 苹黑, font-family"
date: 2015-11-18 23:30
comments: true
header-img: "assets/common/font-bg.jpg"
thumb-img: "assets/common/font-thumb.jpg"
author:     "任平生"
tags:
    - 苹方
    - CSS
    - CSS/font-family
---

随着 El Capitan 和 iOS9 发布而内置新系统中的 [苹方字体](http://www.apple.com/cn/osx/whats-new/#international-fonts) 给我们在中文字体的使用上带来了新的选择。

在 Web 上定义字体为苹方的方法：

``` css
font-family: PingFangSC-Regular, sans-serif;
```



苹方提供了六个字重，font-family 定义如下：

**苹方-简 常规体**

``` css
font-family: PingFangSC-Regular, sans-serif;
```

<div class="code-demo" style="font-family: PingFangSC-Regular, sans-serif;">常规体 示例： 一蓑烟雨任平生 To be or not to be, that is the question</div>



**苹方-简 极细体**

``` css
font-family: PingFangSC-Ultralight, sans-serif;
```

<div class="code-demo" style="font-family: PingFangSC-Ultralight, sans-serif;">常规体 示例： 一蓑烟雨任平生 To be or not to be, that is the question</div>



**苹方-简 细体**

``` css
font-family: PingFangSC-Light, sans-serif;
```

<div class="code-demo" style="font-family: PingFangSC-Light, sans-serif;">细体 示例： 一蓑烟雨任平生 To be or not to be, that is the question</div>



**苹方-简 纤细体**

``` css
font-family: PingFangSC-Thin, sans-serif;
```

<div class="code-demo" style="font-family: PingFangSC-Thin, sans-serif;">纤细体 示例： 一蓑烟雨任平生 To be or not to be, that is the question</div>



**苹方-简 中黑体**

``` css
font-family: PingFangSC-Medium, sans-serif;
```

<div class="code-demo" style="font-family: PingFangSC-Medium, sans-serif;">中黑体 示例： 一蓑烟雨任平生 To be or not to be, that is the question</div>



**苹方-简 中粗体**

``` css
font-family: PingFangSC-Semibold, sans-serif;
```

<div class="code-demo" style="font-family: PingFangSC-Semibold, sans-serif;">中粗体 示例： 一蓑烟雨任平生 To be or not to be, that is the question</div>



苹方除了简体的：苹方-简（PingFang SC），还为繁体用户提供有：苹方-繁（PingFang TC） ，苹方-港（PingFang HK）

**苹方-繁** 的 CSS font-family 使用：

``` css
font-family: PingFangTC-Regular, sans-serif;
font-family: PingFangTC-Ultralight, sans-serif;
font-family: PingFangTC-Light, sans-serif;
font-family: PingFangTC-Thin, sans-serif;
font-family: PingFangTC-Medium, sans-serif;
font-family: PingFangTC-Semibold, sans-serif;
```



**苹方-港** 的 CSS font-family 使用：

``` css
font-family: PingFangHK-Regular, sans-serif;
font-family: PingFangHK-Ultralight, sans-serif;
font-family: PingFangHK-Light, sans-serif;
font-family: PingFangHK-Thin, sans-serif;
font-family: PingFangHK-Medium, sans-serif;
font-family: PingFangHK-Semibold, sans-serif;
```



<style>

.code-demo{

position: relative;

margin: 30px auto;

padding-left: 2em;

}

.code-demo:before{

content: '{';

position: absolute;

left: 0;

top: 50%;

line-height: 110%;

font-size: 3em;

font-family: Helvetica Neue;

opacity: 0.2;

-webkit-transform: translateY(-58%);

}

</style>

