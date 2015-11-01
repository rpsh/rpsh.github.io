---
layout: post
title: 'box-decoration-break 定义换行元素样式'
date: 2014-12-14 13:22
comments: true
author:     "任平生"
tags:
    - CSS3
---
box-decoration-break 可以用来定义换行元素的 `background, padding, border, border-image, box-shadow, margin, clip` 的应用方式。
有两个值： `slice`, `clone` 
`slice` 默认模式；
`clone` 换行的部分具有相同的 `margin, padding, border`，拥有自己的`border-radius, border-image, box-shadow`, 还可以独立地渲染 `background`；

支持状况
<iframe width="100%" height="340" src="http://caniuse.com/css-boxdecorationbreak/embed" frameborder="0"></iframe>


目前使用还需要 `-webkit` 前缀

```
-webkit-box-decoration-break: clone;
box-decoration-break: clone;
```

示例：
<iframe width="100%" height="300" src="http://jsfiddle.net/rpsh/Lrwrye63/embedded/result,html,css/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

参考资料

* [MDN: box-decoration-break](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break)

* [Multi-Line Padded Text](http://css-tricks.com/multi-line-padded-text/)
