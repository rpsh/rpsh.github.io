---
layout: post
title: 'ie8 的 hasLayout'
date: 2011-05-20 10:09
comments: true
categories: 
tags:
    - IE
    - hasLayout
---


今天跟一个同事说 ie8 已经没有 `hasLayout` 了，但却被认为有异议，所以动手实验了一下，在ie8中，检测 block 元素的 `hasLayout`  为 `true`， `inline` 元素的 `hasLayout` 为 `false`。  
但是却不能用之前的触发 ie6/7 hasLayout 的方法去触发了，比如 `zoom:1` ， `height:1%` 等就不能让 ie8 的 `hasLayout` 为 `true`。  
  
可以使用 `element.currentStyle.hasLayout` 来检测其值为 `true` 或者 `false` 
  
个人推测：  
ie8 实际上的确是采用了标准的盒模型放弃了 `hasLayout`，但是却可以使用 `hasLayout` 来检测其是否是 BFC (Block Formatting Context)  
  
参考链接：  
[http://haslayout.net/haslayout][1]  
[http://www.w3help.org/zh-cn/causes/RM8002][2]



[1]: http://haslayout.net/haslayout
[2]: http://www.w3help.org/zh-cn/causes/RM8002