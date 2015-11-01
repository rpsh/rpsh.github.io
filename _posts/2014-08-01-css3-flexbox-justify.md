---
layout: post
title: 'CSS3 实现两端对齐的 justify 布局'
date: 2014-08-01 03:00
comments: true
author:     "任平生"
header-img: "assets/common/css3-bg.jpg"
tags:
    - CSS3
    - CSS/flexbox
    - CSS/justify
---
使用 CSS3 的 flexbox 来实现两端对齐的效果非常容易
<img class="center" src="http://file.rpsh.net/img/201407/flexbox.gif" alt="flexbox">

HTML：

```html
<div class="main">
	<div class="box"></div>
	<div class="box"></div>
	<div class="box"></div>
</div>
```

CSS:

```css
.main{
	/* Android */
	display: -webkit-box;
	-webkit-box-pack: justify;
	
	/* iOS */
	display: -webkit-flex;
	-webkit-justify-content: space-between;

	/* IE10 */
	display: -ms-flexbox;
	-ms-flex-pack:justify;
	
	/* w3c */
	display: flex;
	justify-content: space-between;
}
```

某些情况，在 Android 下， `.box` 元素中的布局可能会不能达到预期，可以针对 `.box` 使用以下 CSS

```css
.box{
	display: -webkit-box;
	-webkit-box-orient: vertical;
}
```
<iframe width="100%" height="180" src="http://jsfiddle.net/rpsh/3Z8nR/embedded/result,html,css/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

参考资料：

- [弹性方框模型 (Flexible Box Model) 快速入门](http://www.html5rocks.com/zh/tutorials/flexbox/quick/)
- [W3C CSS Flexible Box Layout Module](http://www.w3.org/TR/css3-flexbox/)
- [Can I use Flexible Box](http://caniuse.com/#search=flexbox)
- [Internet Explorer 10 中弹性框（“Flexbox”）布局](http://msdn.microsoft.com/zh-cn/library/ie/hh673531(v=vs.85).aspx)
- [Internet Explorer 弹性框（“Flexbox”）布局更新](http://msdn.microsoft.com/zh-cn/library/ie/dn265027(v=vs.85).aspx)
- [Flexible Box 代码生成器](http://the-echoplex.net/flexyboxes/)
