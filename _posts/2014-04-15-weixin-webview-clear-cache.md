---
layout: post
title: "微信 webview 清理缓存方法"
description: "在做微信移动页面开发时若用到清理缓存，iPhone 会很容易，Android 则麻烦一些，方法如下"
keyword: "微信, webview, 清除缓存"
date: 2014-04-15 12:20
comments: true
author:     "任平生"
header-img: "assets/common/wechat-bg.jpg"
thumb-img: "assets/common/wechat-thumb.jpg"
tags:
    - 微信
    - 移动开发
---

在做微信移动页面开发时若用到清理缓存，方法如下

依次打开微信：我－通用－微信 －清理微信存储空间，就可以清理掉 webview 的缓存。

（进入「清理微信存储空间」页面无需任何操作，当点击进入这个页面的时候，微信已经执行了清理缓存的操作）

![微信 webview 清理缓存方法](/assets/2014/04/weixin-cache.jpg)



对于 Android 版微信，目前微信自动使用了 QQ浏览器的 X5 内核，如果上述方法不可以清掉缓存，可以执行如下操作：

在任意聊天窗口发送： [http://debugx5.qq.com](http://debugx5.qq.com) 

打开这个网址，找到清理缓存，点击即可。

 ![x5 清除缓存](/assets/2014/04/x5-clear-cache.jpg)