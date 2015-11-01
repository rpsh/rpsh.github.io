---
layout: post
title: '使用 CSS 将一个页面反色显示'
date: 2014-10-03 10:30
comments: true
author:     "任平生"
header-img: "assets/common/css-bg.jpg"
tags:
    - CSS
    - CSS/trick
---

将一个页面反色

仅 IE9+ 支持

```css
body:before { 
	content:"";
	position:fixed;
	top:50%; left: 50%;
	z-index:9999;
	width:1px; height: 1px;
	outline:2999px solid invert;
}
```

这里利用的 outline 的颜色 `invert` 来实现颜色的反色。


<a href="javascript:(function(){var%20style=document.createElement('style');style.innerHTML='body:before%20{content:%22%22;%20position:fixed;%20top:50%25;%20left:50%25;%20z-index:9999;%20width:1px;%20height:%201px;%20outline:2999px%20solid%20invert;%20}';document.body.appendChild(style)})();" class="view-demo">反色页面</a>


来自： [Invert a whole webpage with CSS only](http://lea.verou.me/2011/04/invert-a-whole-webpage-with-css-only/)