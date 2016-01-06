---
layout: post
title: "移动端 HTML5 页面常见问题 —— 样式篇"
description: "总结移动端网页制作过程中常见的问题，诸如圆角、输入框、滚动条等等"
keyword: "html5, css, 常见问题"
date: 2015-08-27 12:10
comments: true
categories: [HTML]
author:     "任平生"
tags:
    - HTML
    - CSS
    - 移动开发
---

## 问题：Android 上圆形图片使用 border 时，边框显示变形
<img width="320px" src="http://note.rpsh.net/assets/2015/08/radius.png" alt="圆形图片边框变形">

解决：给 img 外嵌套一个元素，为其使用圆角

```html
<div>
	<img src="">
</div>
```

```css
div{
	display: inline-block;
	border-radius: 50%;
	border: 4px solid #FF7000;
}
img{
	vertical-align: top;
}
```

## 问题：Android 上圆角元素，背景颜色会溢出
<img width="320px" src="http://note.rpsh.net/assets/2015/08/border-radius.png" alt="背景色溢出">

解决：

```css
{
	background-clip: padding-box;
}
```

## 问题： Android 上圆角使用 Animation 做 loading 动画时，圆角背景色溢出的bug
<img width="320px" src="http://note.rpsh.net/assets/2015/08/radius-animation-1.gif" alt="圆角溢出">
<img width="320px" src="http://note.rpsh.net/assets/2015/08/radius-animation-2.gif" alt="解决圆角溢出">

解决：

```css
{
	background-color: #F9CEAC;
	border-radius: 32px 0 0 32px;
	-webkit-mask-image: url(http://i.gtimg.cn/qqlive/images/20150527/btn_mask.png);
}
```

原理是使用一个圆角的蒙板通过 `-webkit-mask-image` 遮住多余的部分。蒙板： 
<img style="display:inline-block;vertical-align: bottom;" src="http://i.gtimg.cn/qqlive/images/20150527/btn_mask.png" alt="圆角蒙板">


## 问题：CSS 三角在 Android 上显示为方块
解决：可能是对这个三角使用了圆角，去掉 `border-radius` 即可

```css
{
	border: 10px solid transparent;
	border-left-color: #000;
	/*border-radius: 2px;*/
}
```

##  问题： Android 上使用 svg 作为 background-image 时显示模糊
解决：设置 `background-size`

```css
{
	-webkit-background-size: 100%;
	background-size: 100%;
}
```

##  问题： :active 样式不生效
<img width="320" src="http://note.rpsh.net/assets/2015/08/active.gif" alt="元素 active 样式">

解决： 参考[这篇文章](http://note.rpsh.net/posts/2014/03/18/phone-touch-css-style-active)

```js
document.addEventListener("touchstart", function() {},false);
```


## 问题： 多行文字超出截断需要出现省略号
<img width="320" src="http://note.rpsh.net/assets/2015/08/ellipsis.png" alt="多行文本的超出隐藏省略号">

解决： 参考[这篇文章](http://note.rpsh.net/posts/2014/10/14/css-multiple-line-overflow-ellipsis)

```css
{
	display: -webkit-box;
	overflow: hidden;
	text-overflow: ellipsis;
	-webkit-line-clamp: 2;
	-webkit-box-orient: vertical;
}
```

## 问题： 1px 线条、边框
<img width="320" src="http://note.rpsh.net/assets/2015/08/1px_line.png" alt="1像素边框">

解决：使用高度为 1px ，一半为实色，一半为透明的渐变背景实现

```css
{
	background: -webkit-linear-gradient(top, transparent, transparent 50%, #CACDD0 50%) 0 top no-repeat;
	background-size: 100% 1px;
}
```

如果需要有四个边框都有 1px 的线框，可以使用多背景图

```css
{
	background: -webkit-linear-gradient(top, #CACDD0, #CACDD0 50%, transparent 50%, transparent 100%) 0 top no-repeat,-webkit-linear-gradient(top, transparent, transparent 50%, #CACDD0 50%, #CACDD0 100%) 0 bottom no-repeat, -webkit-linear-gradient(left, #CACDD0, #CACDD0 50%, transparent 50%, transparent 100%) left 0 no-repeat, -webkit-linear-gradient(left, transparent, transparent 50%, #CACDD0 50%, #CACDD0 100%) right 0 no-repeat;
	background-size: 100% 1px,100% 1px, 1px 100%, 1px 100%;
}
```


## 问题：滚动条滚动时没有像 iOS 原生那么顺滑流畅，滚动条没有 iOS 回弹效果
<img width="320" src="http://note.rpsh.net/assets/2015/08/scroll-1.gif" alt="iOS 滚动条">

解决：

```css
{
	overflow: auto;
	-webkit-overflow-scrolling: touch;
}
```
注：在 Android 上由于原生滚动没有回弹效果，所以这里也不会有回弹的效果。


## 问题：当模块使用系统的横向滚动时，不想显示出系统的滚动条样式
<img width="320" src="http://note.rpsh.net/assets/2015/08/scroll-2.gif" alt="隐藏滚动条">

解决：

Android：

```css
::-webkit-scrollbar{
	opacity: 0;
}
```

iOS 要隐藏滚动条，会稍微复杂一些

```html
<div class="wrap">
	<div class="box"></div>
</div>
```

```css
.wrap{
	height: 100px;
	overflow: hidden;
}
.box{
	width: 100%;
	height: -webkit-calc(100% + 5px);
	overflow-x: auto;
	overflow-y: hidden;
	-webkit-overflow-scrolling: touch;
}
```

原理：`.box` 元素的横向滚动条通过其外层元素 `.wrap` 的 `overflow:hide` 来隐藏。 （5px 是 iOS 上滚动条元素的高度）

## 问题：横向滚动的元素，滑动时有时图片显示不出来/文字显示不出来

<img width="320" src="http://note.rpsh.net/assets/2015/08/scroll-3.gif" alt="滑动时元素不显示">

解决：给每个横滑的元素块使用硬件加速

```css
li{
	-webkit-transform: translateZ(0);
}
```

## 问题：使用 animation 动画后，页面上 overflow:auto 的元素滚动条不能滑动
解决：不使用 translate 方式的动画，换为使用 left/top 来实现元素移动的动画

## 问题： 上下滑动页面时候，页面元素消失
解决：检查是否使用了  fadeIn 的 animation，如有则 fill-mode 使用 backwards 模式

```css
{
	-webkit-animation: fadeIn 0.5s ease backwards;
}
```


## 问题：页面上数字自动变成了可以点击的链接
<img width="320" src="http://note.rpsh.net/assets/2015/08/input_tel.gif" alt="数字变为链接">

解决：在页面 `<head>` 里添加 

```html
<meta name="format-detection" content="telephone=no">
```


## 问题：input 在 iOS 中圆角、内阴影去不掉
<img width="320" src="http://note.rpsh.net/assets/2015/08/input.png" alt="去掉 input 的圆角与阴影">

解决：

```css
input{
	-webkit-appearance: none;
	border-radius: 0;
}
```


## 问题：焦点在 input 时，placeholder 没有隐藏
<img width="320" src="http://note.rpsh.net/assets/2015/08/placholder.gif" alt="focus 时隐藏 placholder">

解决：

```css
input:focus::-webkit-input-placeholder{
	opacity: 0;
}
```

## 问题： input 输入框调出数字输入键盘
解决

```html
<input type="number" />
<input type="number" pattern="[0-9]*" />
<input type="tel" />
```
分别对应下图中的1、2、3。

<img width="95%" src="http://note.rpsh.net/assets/2015/08/keyboard_number.png" alt="圆形图片边框变形">

需要注意的是，单独使用 `type="number"` 时候， iOS 上出现并不是九宫格的数字键盘，如果需要九宫格的数字键盘，可选择使用 2、3 的方法。
1、2、3 在 Android 上均可以唤起九宫格的数字键盘


## 问题：搜索时，键盘的回车按钮文字设定为“搜索”
<img width="320" src="http://note.rpsh.net/assets/2015/08/form_search.png" alt="定义键盘回车文案为搜索">

解决： `input` 使用 `type="search"`，放在 `form` 表单内。两者结合就能使输入法中的回车按钮文字变为“搜索”

```html
<form action="">
		<input type="search" />
</form>
```


## 问题：iframe 在 iOS 上没有滚动条，直接撑出去
<img width="320" src="http://note.rpsh.net/assets/2015/08/iframe.png" alt="iframe 撑出界面">

解决：给 iframe 外嵌套一个 div， 为这个 div 设置固定高度与 `overflow`

```html
<div>
	<iframe src=""></iframe>
</div>
```
```css
div{
	height: 100px;
	overflow: auto;
	-webkit-overflow-scrolling: touch;
}
```