---
layout: post
title: "Chrome(Webkit)中伪元素不支持动画的bug修复了"
description: "webkit 中伪元素（pseudo element）不支持动画（transition 和 animation ）的bug终于修复了（Chrome  26）。这真是一个漫长的过程啊。  "
keyword: "chrome, 伪元素"
date: 2013-01-13 15:05
comments: true
header-img: "assets/common/chrome-bg.jpg"
thumb-img: "assets/common/chrome-thumb.jpg"
author:     "任平生"
tags:
    - Chrome
    - CSS
---


webkit 中伪元素（pseudo element）不支持动画（transition 和 animation ）的bug终于[修复][1]了（Chrome  26）。这真是一个漫长的过程啊。  
  
不过当前稳定版本的Chrome 24，看来等稳定版本升级到26还得一段时间。  
  
  
这样除了 Opera 所有主流浏览器的最新版本都可以支持伪元素的动画行为了。  
  
  
需要注意的是，IE10 中，伪元素对动画的支持有一个bug：  
  
```css
.x:hover:before { /* 不起任何作用 */ }
  
.x:hover {}  
.x:hover:before { /* 起效（需要 :hover 来激活） */ }
```

  
参考资料：

* [http://css-tricks.com/pseudo-element-animationstransitions-bug-fixed-in-webkit/][2]  
* [http://css-tricks.com/transitions-and-animations-on-css-generated-content/][3]  
* [http://css-tricks.com/pseudo-element-roundup/][4]  
  


[1]: http://trac.webkit.org/changeset/138632
[2]: http://css-tricks.com/pseudo-element-animationstransitions-bug-fixed-in-webkit/
[3]: http://css-tricks.com/transitions-and-animations-on-css-generated-content/
[4]: http://css-tricks.com/pseudo-element-roundup/