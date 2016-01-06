---
layout: post
title: "IE10 的 HTML5 怪异模式"
description: "微软将 IE10 中默认的怪异模式称之为： HTML5 怪异模式（HTML5 Quirks Mode），一方面它遵循HTML5 定义的渲染规则，同时也遵守怪异模式的渲染规则"
keyword: "IE10, 渲染模式"
date: 2011-12-15 16:02
comments: true
header-img: "assets/common/ie-bg.jpg"
thumb-img: "assets/common/ie-thumb.jpg"
author:     "任平生"
tags:
    - IE
    - IE10
    - 渲染模式
---


微软将 IE10 中默认的怪异模式称之为： HTML5 怪异模式（HTML5 Quirks Mode），一方面它遵循 [HTML5 定义的渲染规则][1]，同时也[遵守][2][怪异模式][3]的[渲染][4][规则][5]。在以下两种情况，IE10 会进入这种 HTML5 怪异模式：  

> 一、没有文档声明  
> 二、使用传统的 [HTML文档声明][6]

  
此外，当今的现代浏览器（Firefox，Chrome等），在即使没有文档声明的情况下，也会以（准）标准模式渲染页面。这次，IE10也开始遵循此点。这样就保证了没有文档声明的网页在所有浏览器中渲染都是一样的。  
  
当然，我们伟大的微软，向来以周全考虑为己任为首要任务的微软，为了兼顾那些不规范的网页，又搞出了一个 IE5 兼容模式，以这个模式渲染的页面就是以往 IE 的怪异模式（工程师们你伤不起的啊）。  
  

![IE5 模式](http://note.rpsh.net/assets/2011/12/HTML5QuirksModeinIE10.png)

  
开启这个模式的代码是：  

`<meta http-equiv="X-UA-Compatible" content="IE=5">`

（喂！没有文档声明的网页还有人维护吗？还有人维护吗？维护吗？吗？）  
（另外，这样那些无人维护的页面岂不是在 IE10 下边渲染会像当初的 Firefox 吗，微软你考虑的真的周到吗 ）  
  
  
来源：[http://blogs.msdn.com/b/ie/archive/2011/12/14/interoperable-html5-quirks-mode-in-ie10.aspx][7]

[1]: http://blogs.msdn.com/b/ie/archive/2011/07/06/html5-parsing-in-ie10.aspx
[2]: http://dev.w3.org/html5/spec/links.html#case-sensitivity
[3]: http://dev.w3.org/html5/spec/rendering.html#flow-content-1
[4]: http://dev.w3.org/html5/spec/rendering.html#form-controls
[5]: http://dev.w3.org/html5/spec/rendering.html#images
[6]: http://dev.w3.org/html5/spec/tree-construction.html#the-initial-insertion-mode
[7]: http://blogs.msdn.com/b/ie/archive/2011/12/14/interoperable-html5-quirks-mode-in-ie10.aspx