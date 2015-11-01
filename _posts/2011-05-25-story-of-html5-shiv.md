---
layout: post
title: 'HTML5 Shiv 的一些趣事'
date: 2011-05-25 03:15
comments: true
categories: 
tags:
    - HTML5
    - 趣识
---


我敢肯定，你一定没听说过 [Sjoerd Visscher][1] 这个名字，虽然你天天在熟练地用着 HTML5 Shiv 去修复 IE 不能识别未知元素的bug。  
  
2002年，荷兰海牙。 Visscher 在改进 XSL 的显示样式的过程中发现，非HTML元素不能应用CSS样式。  
  
2008年，HTML5 已经出现了，一些新的元素被提出并应用，但是 IE 6-8 不能识别未知元素，这些新元素不能作为父节点包裹子元素，并且不能应用CSS样式。这个悲剧的现实将 HTML5 的实际应用拖入寸步难移的泥淖当中。  
  
这时候， W3C HTML工作组的联合主席 Sam Ruby 在他的 Blog 上收到了一条 Sjoerd 的[评论][2]：（2008.01.22）  

> _Btw, if you want CSS rules to apply to unknown elements in IE, you just have 
> to do document.createElement(elementName). This somehow lets the CSS engine 
> know that elements with that name exist_

> 在IE中，如果你想将 CSS 样式应用在未知元素上，只需执行 document.createElement(elementName) ，如此这般后，CSS引擎就能识别这个元素了。 
> 

HTML5 规范的主编，Ian Hickson 被这个鬼斧神工般的技巧给震撼了，然后激动地[说][3]：这项技术扫清了通往HTML5大路上的最大障碍，让在 IE 上兼容实现HTML5指日可待。  
  
一天后，John Resig 就写了一篇[文章][4]，并创造了 "HTML5 Shiv" 这个词。嗯，准确地说应该叫做 shim，John随后也承认了这是一个拼写错误。但是 HTML5 Shiv 真的像一把尖刃(Shiv)斩开了拦在 HTML5 大道上的荆棘。  
  
  
HTML5 Shiv 简史：  
  

* 2009.01 Remy Sharp 创建了第一个[让IE支持 HTML5 标签元素的脚本][5]
* 2009.06 Faruk Ates 在 Modernizr 中引入 html5shiv
* 2010.02 众多 Javascript 大牛，Remy, Kangax, John David Dalton 和 PorneL都参与进来[优化这段脚本][6]的大小
* 2010.03 Mathias Bynens 等人发现 shiv 在打印页面并不能生效，那一天是相当滴灰暗，不过也激发了开发者的斗志去挑战这个难题
* 2010.04 Jonathan Neal 带着[ IE Print Protector (IEPP) ][7]成功挑战了这个难题，巧妙地使用 onbeforeprint 和 onafterprint 事件将 shiv “运用”在了打印页面上
* 2010.04 Remy 发布了带 IEPP 的 html5shiv 
* 2011.02 IEPP 的接力棒传到了 Alexander Farkas 手中，他将项目转移到 [github][8] 上，添加了测试套件，修复bug，改进性能
* 2011.04 IEPP v2 发布，Modernizr 和 html5shiv 也跟进引入了最新版。

  
  
最后，为 HTML5 Shiv 添砖添瓦的人有：[Sjoerd Visscher][1], [Sam Ruby][9], [John Resig][10], [Remy Sharp][11], [Faruk Ates][12], [Kangax][13], [John David Dalton,][14] [PorneL][15], [Mathias Bynens][16], [Paul Irish][17](本文作者), [Jonathan Neal][18] 以及 [Alexander Farkas][19]  
  
  
原文：[http://paulirish.com/2011/the-history-of-the-html5-shiv/][20]

[1]: https://twitter.com/sjoerd_visscher
[2]: http://intertwingly.net/blog/2008/01/22/Best-Standards-Support#c1201006277
[3]: http://ln.hixie.ch/?start=1201080691&count=1
[4]: http://www.blogger.com/
[5]: http://remysharp.com/2009/01/07/html5-enabling-script/
[6]: http://mathiasbynens.be/demo/html5-shims
[7]: http://www.iecss.com/print-protector/
[8]: https://github.com/aFarkas/iepp/wiki
[9]: http://intertwingly.net/blog/
[10]: http://ejohn.org/blog/
[11]: http://remysharp.com/
[12]: http://farukat.es/
[13]: http://perfectionkills.com/
[14]: http://allyoucanleet.com/
[15]: http://pornel.net/
[16]: http://mathiasbynens.be/
[17]: http://paulirish.com/
[18]: http://twitter.com/jon_neal
[19]: https://github.com/afarkas
[20]: http://paulirish.com/2011/the-history-of-the-html5-shiv/