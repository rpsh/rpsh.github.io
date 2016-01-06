---
layout: post
title: "纯 CSS 实现实时动态毛玻璃效果"
description: "iOS9 支持使用 css3 来实现动态毛玻璃效果：-webkit-backdrop-filter"
keyword: "毛玻璃, ios9新特性, css3, backdrop-filter"
date: 2015-07-30 12:18
comments: true
author:     "任平生"
header-img: "assets/common/css3-bg.jpg"
thumb-img: "assets/common/css3-thumb.jpg"
tags:
    - CSS3
    - CSS
    - 毛玻璃
---
目前在 Web 上实现毛玻璃效果一般是通过一个大截屏图片的高斯模糊加上滚动位置的切换来[实现](http://www.zhihu.com/question/30502281)，而在 iOS9 和 OS X 10.11 的 Safari 原生支持了 CSS 的 `backdrop-filter` 来实时地生成一个毛玻璃效果的背景。

<img src="http://note.rpsh.net/assets/2015/07/live-blur.gif" alt="live-blur.gif" />



代码：

```css
{
	-webkit-backdrop-filter: blur(10px);
}
```
目前还需要 `webkit` 的前缀。

除了 `blur`, `backdrop-filter` 还有以下这些属性
- blur()
- brightness()
- contrast()
- drop-shadow()
- grayscale()
- hue-rotate()
- invert()
- opacity()
- saturate()
- sepia()

用法跟 filter [相似](https://drafts.fxtf.org/filters/#typedef-filter-function-list)：

```css
{
	-webkit-backdrop-filter: blur(10px) brightness(1.2) contrast(0.3);
}
```
不仅是普通的图片，实时播放的视频也能实现毛玻璃：

<video muted style="margin:auto;display:block;" width="375" height="333" autoplay src="http://itltcdn.b0.upaiyun.com/demo/ios9-blur.mp4" loop ></video>

最后放一个 demo：(iOS9、OS 10.11 Safari 可以体验)

<img style="display:block;margin:auto;" src="http://note.rpsh.net/assets/2015/07/live-blur-qr.png" alt="live-blur-qr.png" width="200" height="200" />


<iframe height="301" scrolling="no" src="//codepen.io/rpsh/embed/OVaYQV/?height=301&amp;theme-id=0&amp;default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true" style="width: 100%;"></iframe>


参考资料：

[Safari 9.0](https://developer.apple.com/library/mac/releasenotes/General/WhatsNewInSafari/Articles/Safari_9.html)
