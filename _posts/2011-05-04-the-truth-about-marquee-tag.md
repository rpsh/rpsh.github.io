---
layout: post
title: '有关 &lt;marquee&gt; 标签的一些现实'
date: 2011-05-04 07:28
comments: true
categories: 
tags:
    - HTML
    - 有趣的事实
---


今天发现了一个蛋疼的现实：  
`<marquee>` 是被各个浏览器都支持的，我记得当初之所以不建议大家在代码中使用 marquee 的原因就是这个东西只有 ie 支持，是非标准的标签... 那么现在呢？ 当 HTML5 越来越以现实需求为中心，当 a 标签都可以包裹 h1, p, div 的时候， marquee 真的有那么邪恶吗？  
  
在非ie浏览器中并不一定需要 `<marquee>` 标签来实现跑马灯效果。  
  
chrome 跑马灯效果生效的真正属性是： `overflow : -webkit-marquee`  
  
而 firefox 中则是使用 `-moz-binding` 来实现的 [developer.mozilla.org/en/CSS/-moz-binding][1]  
  
opera 是通过 `display : -wap-marquee` 来实现；  
  
如果在 CSS 中定了上述几个属性，那么将会导致在某个浏览器中跑马灯效果失效。  
  
最后，这个标签还被 iOS 中的 safari 支持！  
  
  
注： -wap- 前缀是 mobile css 中引入的 [dev.opera.com/articles/view/mobile-style-css-mobile-profile-2-0/][2] 



[1]: https://developer.mozilla.org/en/CSS/-moz-binding
[2]: http://dev.opera.com/articles/view/mobile-style-css-mobile-profile-2-0/