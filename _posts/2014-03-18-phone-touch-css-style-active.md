---
layout: post
title: "iPhone 上CSS定义 active 样式"
description: "如果给按钮定义 :hover 样式，在 iPhone 上按钮点击一次是 hover 态，再点击一次 hover 态才会消失，这显然不是我们想要的，继而想通过定义 :active 样式来实现按钮按下时的效果，但发现定义的 active 样式在 iPhone 上点击时没有任何效果。 "
keyword: "css, active, ontouchstart, touchstart"
date: 2014-03-18 14:03
comments: true
author:     "任平生"
header-img: "assets/common/css-bg.jpg"
thumb-img: "assets/common/css-thumb.jpg"
tags:
    - CSS
    - iOS
---
如果给按钮定义 `:hover` 样式，在 iPhone 上按钮点击一次是 hover 态，再点击一次 hover 态才会消失，这显然不是我们想要的，继而想通过定义 `:active` 样式来实现按钮按下时的效果，但发现定义的 active 样式在 iPhone 上点击时没有任何效果。 搜索后发现，只需添加一段 js 即可：

```js
document.addEventListener("touchstart", function() {},false);
```

另一个方案，可以在 body 上添加 `ontouchstart=""`

```html
<body ontouchstart="">
```

[原理](http://alxgbsn.co.uk/2011/10/17/enable-css-active-pseudo-styles-in-mobile-safari/ "Enable CSS active pseudo styles in Mobile Safari")：Safari 默认禁用了元素的 `active` 样式，我们通过声明 `touchstart`  来覆盖默认事件，就可以让 `active`  样式重新激活。

此外，默认点击按钮会有一个灰色的外框，通过这段 CSS 可以清除：

```
html {
	-webkit-tap-highlight-color: rgba(0,0,0,0);
}
```
