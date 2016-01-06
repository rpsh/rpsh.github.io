---
layout: post
title: "font-size 的 px em 与 rem 的区别"
description: "em 以父节点作为标准计算， rem 以根节点 html 来计算字体大小"
keyword: "rem, em, css"
date: 2011-05-03 08:25
comments: true
header-img: "assets/common/css-bg.jpg"
thumb-img: "assets/common/css-thumb.jpg"
author:     "任平生"
tags:
    - CSS
    - CSS/rem
---


之前看到说 px 与 em 的区别是 px 在 ie 里不能放大，但是我用 ctrl 滚动鼠标放大页面，文字是可以放大的嘛，就一直以为这个是以讹传讹的错误理论；  
  
今天看了Jonathan Snook 的[文章][1]，才注意到，这个放大文字，是指浏览器自带的 文字大小 的调整功能，并不是放大整个页面，在ie中，调整文字的功能是这个：  

![text-zoom.png](http://note.rpsh.net/assets/2011/05/text-zoom.png)

  
OK，那么一切就明了了。 如果使用 px 作为字体大小的单位，那么在 ie 下边，当通过上述方法在浏览器中设置大字号的文字 并不能生效，即使在 ie9 中也不能。  
  
任何默认浏览器的字体大小都是 16px ，当设置 body 的 font-size:62.5% 的时候， 1em = 10px; 1.2em = 12px;  
  
em 单位的特点：  
  

* em 值不是固定的
* em 会根据父级元素的大小来进行计算；

  
使用 em 时候有个很严重的问题，看代码：  
  
```css    
body { font-size:62.5%; }  
h1 { font-size: 2.4em; } /* =24px */  
p  { font-size: 1.4em; } /* =14px */  
li { font-size: 1.4em; } /* =14px? */  
```

如果一个 li 中又出现了一个列表 ul  li ，那么这个 li 将会是 20px，如果其中再嵌套了一个 ul li，这将会是一种噩梦...  
  
所以，在 css3 中，提出了一个新的单位来解决这个问题： rem  ( root em )  
根据根元素来计算em的值； 根元素也就是 <html>  
所以代码可以是：  
  
```css  
html { font-size:62.5%; }  
h1 { font-size: 2.4rem; } /* =24px */  
p  { font-size: 1.4rem; } /* =14px */  
li { font-size: 1.4rem; } /* =14px */  
```
  
  
问题解决了，世界清静了  :P  
  
注： opera 尚不支持 rem； ie9、chrome、firefox、safari 都已经支持 rem；  
  
参考链接：  
[http://snook.ca/archives/html_and_css/font-size-with-rem][1]

[1]: http://snook.ca/archives/html_and_css/font-size-with-rem
[2]: http://2.bp.blogspot.com/-QZ8ZgA895u4/Tb-4ACSfzOI/AAAAAAAACRI/JQR4KDfaEd8/s1600/text-zoom.png