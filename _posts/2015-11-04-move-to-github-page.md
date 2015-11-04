---
layout: post
title: '迁移至 Github Pages'
date: 2015-11-04 11:30
comments: true
header-img: "assets/common/home-bg.jpg"
author:     "任平生"
tags:
    - Github Page
    - Google
    - Baidu
    - 站内搜索
---

由于 [note.rpsh.net](http://note.rpsh.net) 在 [logdown](https://logdown.com) 付费帐号（可以绑定自定义域名）到期，就准备再折腾一下，将这个笔记再继续迁移一下，尝试了 Ghost、 Hexo 后决定搬移到 Github Pages（ 这样以后简历也能写上熟练使用 Github 了 😂 ）

这个模版来自 [Hux](http://huangxuan.me/)， 整体设计感很赞，于是拿来改一改增加了 Disqus 评论、站内搜索。

本来以为不会折腾的，但是在做站内搜索时候，才发现还是必须要折腾一下。

因为 Jekyll 程序不能提供全文检索的搜索功能，于是还是要找回万能的 Google，通过 Google [Custom Search Engine(CSE)](https://cse.google.com/) 来完成站内搜索。

Google CSE 提供了丰富的接口及回调，而且可以简单的通过 CSS 修改样式，达到与站点自身风格的一致。

体验站内搜索： [http://note.rpsh.net/search/](http://note.rpsh.net/search/)

<img src="http://note.rpsh.net/assets/2015/11/google-site-search.jpg" alt="Google 站内搜索" />

完成后，有个萦绕的想法就是要给那些不能顺畅使用 Google 的访客也能有一个「后备」的搜索方案，于是找了一圈， 发现只有百度有提供基本可用的自定义[站内搜索接口](http://zn.baidu.com/)。

但是百度的站内搜素只提供了很少的自定义功能，而且搜索结果是用 iframe 形式展示的，能对其样式进行的修改微乎其微，只能聊胜于无，GFW 受害者，麻烦凑合着用吧 🙁

<img src="http://note.rpsh.net/assets/2015/11/baidu-site-search.jpg" alt="Baidu 站内搜索" />
