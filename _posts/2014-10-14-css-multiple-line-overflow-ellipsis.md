---
layout: post
title: '纯CSS实现多行文本截断并有省略号'
date: 2014-10-14 06:35
comments: true
author:     "任平生"
header-img: "assets/common/js-bg.jpg"
tags:
    - CSS
    - CSS/ellipsis
---
单行文本截断并末尾出现省略号一般写法是：

```css
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;
```

多行文版截断并出现省略号的纯CSS解决一直是个“复杂的难题“，不过有个“被废弃”的 webkit 私有属性反而可以实现，而且在移动端的兼容性不错， iOS 与 Android 均有不错的支持

```css
display: -webkit-box;
overflow: hidden;
text-overflow: ellipsis;
-webkit-line-clamp: 2;
-webkit-box-orient: vertical;
```

其中的 `-webkit-line-clamp: 2` 即用来控制文本超出两行时截断并出现省略号。 在使用中如果出现第三行文字露一点头出来的问题，设置合理的 `line-height` 即可解决。

<iframe width="100%" height="180" src="//jsfiddle.net/rpsh/4aokpuf6/embedded/result,html,css/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>


多行省略号用在 a 链接中时会有一个bug，省略号出现在文字中间：

![链接中多行省略号bug](/assets/2014/10/ellipsis_in_link.jpeg)



这个问题的解决方案是，不要将多行省略的属性写在 a 上（或其父标签）。而在 a 内再嵌套一个标签，对其使用多行省略。

```html
<a href="#"><div>Lorem ipsum dolor sit amet</div></a>
```

```css
a div{
	display: -webkit-box;
	overflow: hidden;
	text-overflow: ellipsis;
	-webkit-line-clamp: 2;
	-webkit-box-orient: vertical;
}
```

参考资料：
[Line Clampin’ (Truncating Multiple Line Text)](https://css-tricks.com/line-clampin/)