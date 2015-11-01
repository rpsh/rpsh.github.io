---
layout: post
title: '微信 webview 清理缓存方法'
date: 2014-04-15 12:20
comments: true
author:     "任平生"
header-img: "assets/common/wechat-bg.jpg"
tags:
    - 微信
    - 移动开发
---
在做微信移动页面开发时若用到清理缓存，iPhone 会很容易，Android 则麻烦一些，方法如下

iOS:
双击 Home 键，退出微信程序，然后重新打开微信即可。

Android:
1、依次打开：设置－应用程序管理－微信
2、点击：清除缓存
3、点击：强制停止
4、重新打开微信

![微信 webview 清理缓存方法](/assets/2014/04/weixin-cache.jpg)


对于 Android 版微信，还有一种情况：如果安装了 QQ浏览器，微信的 Webview 会调用 QQ浏览器。这时候要清缓存的话，需要在QQ浏览器里清缓存。
