---
layout: post
title: "IE兼容性列表（Compatibility View List）"
description: "在 IE8 中，微软通过 Windows Update 来更新这个兼容性列表；而在 IE9 中，微软开始通过一个 xml 文件来控制。"
keyword: "IE, 兼容性列表"
date: 2013-01-30 08:08
comments: true
author:     "任平生"
header-img: "assets/common/ie-bg.jpg"
thumb-img: "assets/common/ie-thumb.jpg"
tags:
    - IE
    - 渲染模式
---


IE兼容性列表： 

* IE8兼容性列表：[http://www.microsoft.com/en-us/download/details.aspx?id=16599][1]  
* IE9兼容新列表：[http://ie9cvlist.ie.microsoft.com/ie9CompatViewList.xml][2]  
  
本地的兼容性列表：（Win+R，输入打开）  

* IE8： res://iecompat.dll/iecompatdata.xml  
* IE9： File:\\%LOCALAPPDATA%\Microsoft\Internet Explorer\IECompatData\iecompatdata.xml  
  
在 IE8 中，微软通过 Windows Update 来更新这个兼容性列表；而在 IE9 中，微软开始通过一个 xml 文件来控制。据微软说这个控制将更加灵活，如果你确信你的网站在 IE9+ 中表现正常就可以写邮件给 iepo@microsoft.com ，将自己的网址从这个列表中移除  
  
参考资料：  
[http://msdn.microsoft.com/en-us/library/gg622935(v=VS.85).aspx][3]



[1]: http://www.microsoft.com/en-us/download/details.aspx?id=16599
[2]: http://ie9cvlist.ie.microsoft.com/ie9CompatViewList.xml
[3]: http://msdn.microsoft.com/en-us/library/gg622935(v=VS.85).aspx