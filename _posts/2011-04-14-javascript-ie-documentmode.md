---
layout: post
title: 'javascript: 判断 IE 的渲染模式 及 判断浏览器标准渲染模式的方法'
date: 2011-04-14 06:34
comments: true
header-img: "assets/common/ie-bg.jpg"
author:     "任平生"
tags:
    - JS
    - IE
    - 浏览器
    - 渲染模式
---

**判断 ie 是使用ie9、ie8、ie7 哪种模式渲染的方法**： 
`document.documentMode`
如果没有文档声明，则返回数字 5  
  
只有ie8、ie9可以使用此方法；  
ie6 、非IE浏览器使用 `document.documentMode` 都将返回 `undefined`；  
  
**判断文档是否使用标准模式进行渲染的方法**：`document.compatMode`  
标准模式将返回：`CSS1Compat`  
怪异模式将返回：`BackCompat`  
  
准标准模式也会返回 `CSS1Compat`，所以这个方法只能判断浏览器是否工作在“怪异模式”下，但是由于准标准模式和标准模式之间差异不大，所以这个方法依然被广泛用来判断浏览器是否工作在标准模式下。  
  
小史：`document.compatMode` 最早出现在 ie6 中，后来被所有的主流浏览器采用。  
  
参考链接：  
[http://www.quchao.com/entry/detect-browser-by-features/][1]  
[http://msdn.microsoft.com/en-us/library/cc196988(v=vs.85).aspx][2]  
[http://www.whatwg.org/specs/web-apps/current-work/multipage/dom.html#dom-document-compatmode][3]  
[http://www.w3help.org/zh-cn/kb/001][4]

[1]: http://www.quchao.com/entry/detect-browser-by-features/
[2]: http://msdn.microsoft.com/en-us/library/cc196988(v=vs.85).aspx
[3]: http://www.whatwg.org/specs/web-apps/current-work/multipage/dom.html#dom-document-compatmode
[4]: http://www.w3help.org/zh-cn/kb/001