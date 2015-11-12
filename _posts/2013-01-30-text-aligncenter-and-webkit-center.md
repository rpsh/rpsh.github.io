---
layout: post
title: "text-align:center 与 -webkit-center/-moz-center 的区别"
description: "text-align:center 与 text-align:-webkit-center/-moz-center 的区别"
keyword: "-webkit-center, -moz-center"
date: 2013-01-30 07:28
comments: true
author:     "任平生"
header-img: "assets/common/css-bg.jpg"
thumb-img: "assets/common/css-thumb.jpg"
tags:
    - CSS
---

`text-align:center` 与 `text-align:-webkit-center/-moz-center` 的区别：  

<iframe allowfullscreen="allowfullscreen" frameborder="0" src="http://jsfiddle.net/rpsh/yZypN/embedded/result,css,html/" style="height: 340px; width: 100%;overflow:hidden"></iframe>

  
如上例。  
`text-align:center` 只能让 `inline` 元素居中，而不能让 `block` 元素居中；  
`text-align:-webkit-center` 可以让其中的 `block` 元素也可以居中；  
  
_当然，在例一中，给内部的 `block` 元素设置 `margin:auto` 也可以让 `block` 元素居中_。  
  
**浏览器支持情况**：  
支持：Chrome1.0+、Firefox3.6+ 、Safari1.0+  
不支持：IE、Opear


参考资料：

[MDN: text-align](https://developer.mozilla.org/zh-CN/docs/CSS/text-align)

