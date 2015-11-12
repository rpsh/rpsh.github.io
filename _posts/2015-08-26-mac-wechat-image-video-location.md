---
layout: post
title: "Mac/Windows版微信聊天图片、视频文件存储位置"
description: "如何找到微信软件在 Mac/Windows 本地存储的聊天信息文件位置，从而轻松地提取出其中的图片、视频、小视频、音频等文件"
keyword: "微信Mac版, 微信聊天信息位置, 微信聊天记录位置, 微信聊天记录存储文件夹, 微信聊天记录文件导出"
date: 2015-08-26 01:58
comments: true
author:     "任平生"
header-img: "assets/common/wechat-bg.jpg"
thumb-img: "assets/common/wechat-thumb.jpg"
tags:
    - Mac
    - 微信
---

Mac 版微信收到的小视频默认不能保存到本地，而我们只要找到其在 Mac 上的存储位置就可以直接拿到视频文件。

微信聊体视频本地存储位置：

`~/Library/Containers/com.tencent.xinWeChat/Data/Library/Application Support/Wechat/1.2/{一串字符}/Message/MessageTemp/{一串字符}/Video`

微信聊体图片本地存储位置：

`~/Library/Containers/com.tencent.xinWeChat/Data/Library/Application Support/Wechat/1.2/{一串字符}/Message/MessageTemp/{一串字符}/Image`


使用 Windows 版微信的同样可以拿到微信在本地存储的聊天记录中的文件内容，在 Windows 系统存储的位置是：

`C:\Users\{用户名}\Documents\WeChat Files\{微信名}` 

or

`%userprofile%\Documents\WeChat Files\{微信用户名}` 

这个文件夹下有：视频、音频、图片等都可以找到。
