---
layout: post
title: 'App Store 链接中的 mt=8 是什么意思'
date: 2014-03-26 13:34
comments: true
author:     "任平生"
tags:
    - App Store
---

常见到 iOS App 发出来的下载链接最后都会跟一个 `?mt=8` 的尾巴，这是什么意思呢？在 Stackoverflow 上找到了[答案](http://stackoverflow.com/questions/1781427/what-is-mt-8-in-itunes-links-for-the-appstore "What is “mt=8” in iTunes links for the appstore?")：



mt = Media Type
而数字的对应关系如下：

	1   Music
	2   Podcasts
	3   Audiobooks
	4   TV Shows
	5   Music Videos
	6   Movies
	7   iPod Games
	8   Mobile Software Applications
	9   Ringtones
	10  iTunes U
	11  E-Books
	12  Desktop Apps

所以 `?mt＝8` 意思就是媒体类型是移动软件应用。

根据 mt 参数， iOS 可以判断启动哪个应用，比如 8 对应 App，这时候应该打开 App Store，而 11 就是电子书，应该使用 iBooks 打开，而 2 是 Podcast，需要使用 Podcast 应用打开，等等。

如果不使用 mt 参数，比如一个电子书应用的链接：https://itunes.apple.com/cn/book/hong-lou-meng/id574232640 ，你可以看到它先在 iTunes 或 App Store 里打开，然后再切换到 iBooks 应用。（在 iOS6 上经常遇到这个问题，而 iOS7 似乎不加 mt 参数也可以一次性打开正确的对应应用了）