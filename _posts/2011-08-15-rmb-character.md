---
layout: post
title: "人民币符号 ¥ 一横还是两横的问题"
description: "关于人民币符号到底是一横还是两横，根据人民币（100或50）银线上印的符号可以确定这个符号应该用两横的。"
keyword: "人民币符号"
date: 2011-08-15 10:36
comments: true
author:     "任平生"
tags:
    - CSS/font-family
    - 人民币
---


今天在看[嗷嗷博客][1]的时候又看到了这个问题，关于人民币符号到底是一横还是两横，根据人民币（100或50）银线上印的符号可以确定这个符号应该用两横的。  
  
  
恩，接下来，回顾一下为什么会产生这个问题。  
  
我们一般是这样打出这个符号：中文输入状态下，shift+4 ，出来的就是 `￥` 。  
  
这个字符 Unicode Character Code 编码是：`FFE5`（字符实体 `&#65509`），在使用 `simsun，arial, tahoma，verdana` 字体时显示的都是一道杠的模样 `￥` 。  
所以，对于中文用户来说，默认看到的可能都会是一横的符号 —— 因为中文用户系统默认字体是宋体/Arial —— 这就让大家产生了一种错觉，以为一横的符号才是正确的。_（需要注意的是，在 IE8+， Chrome 上， arial 字体的 ￥ 也表现为两横）_  
  
但是，如果对这个字符使用微软雅黑（Microsoft YaHei），华文细黑（STXihei），細明體（MingLiu）字体时，这个字符又表现出了**两横**的生命体征 ￥， 纠结的人民币符号，你伤不起啊。  
  
好吧，直接打出来的字符这么纠结的现状，那么我们用标准的人民币符号，其实呢，人民币符号是“山寨” 日元符号 ¥ 来的，所以，我们可以用这个日元符号的字符实体 `&yen;` 来实现统一的两横。  
  
`&yen;` 的 Unicode Character Code编码是：A5 ，看着牛逼闪闪的编码就可以知道这货绝对是正品 ANSI 编码，不是 Unicode 扩展出来的山寨版。  
  
使用字符实体 `&yen;` 在包括 simsun, arial 等字体下都能轻松显示两横无压力。  
  
  
有个特例就是 tahoma 字体，无论是用 `&yen;` 还是 `&#65509;` 都显示为一横： `¥` ，彻底的伤不起了～  
  
综上，建议使用 `&yen;` 来表示人民币符号，字体避免使用 tahoma 字体。



[1]: http://www.aoao.org.cn/blog/2010/03/rmb/