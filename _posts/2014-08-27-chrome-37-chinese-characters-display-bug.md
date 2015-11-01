---
layout: post
title: '解决 Chrome 37 中文汉字不显示的bug'
date: 2014-08-27 15:35
comments: true
author:     "任平生"
header-img: "assets/common/chrome-bg.jpg"
tags:
    - Chrome
    - Chrome/classList
---
更新 Chrome 到 37 后，发现很多网页的汉字都不显示了：

![chrome-37-bug.png](/assets/2014/08/chrome-37-bug.png)


解决办法：
打开： `chrome://flags/#disable-direct-write`
将「停用 DirectWrite」选项，设置为启用。
重启 Chrome 问题解决。

参考资料：
[DirectWrite 是什么](http://msdn.microsoft.com/zh-cn/library/windows/desktop/dd371554(v=vs.85).aspx)