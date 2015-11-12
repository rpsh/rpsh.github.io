---
layout: post
title: "ol 有序列表序号的倒序"
description: "原来 OL 有序列表还可以定义序号的起始数字呢。不过在 HTML4 规范中是被废弃的，但「神奇」的是浏览器却都支持这个属性。"
keyword: "有序列表"
date: 2011-12-27 16:00
comments: true
author:     "任平生"
header-img: "assets/common/html-bg.jpg"
thumb-img: "assets/common/html-thumb.jpg"
tags:
    - HTML
---


今天看了[这篇][1]的文章，才知道原来 OL 有序列表还可以定义序号的起始数字呢。不过在 HTML4 规范中是被废弃的，但「神奇」的是浏览器却都支持这个属性。于是，你懂得，在 HTML5 中它就又重新被纳入规范。并且，在 HTML5 中为有序列表增加量了一个新属性：reversed 。通过 reversed 属性来定义_**列表序号**_为倒序，比如：100，99，98……  
  
  
通过 start 属性定义有序列表的开始序号：

  
```html
<ol start="100">  
	<li>list item one</li>  
	<li>list item two</li>  
	<li>list item three</li>  
	<li>list item four</li>  
	<li>list item five</li>  
</ol>  
```

		  
显示效果：  

![列表项序号](/assets/2011/12/start-list.jpg)

  
  
直接通过 value 定义 序号


```html
<ol>  
	<li value="100">list item one</li>  
	<li value="101">list item two</li>  
	<li value="102">list item three</li>  
	<li value="103">list item four</li>  
	<li value="104">list item five</li>  
</ol>
```



可以达到上例同样的效果。  
  
  
新增的 reversed 属性：  

```html
<ol reversed>  
	<li>list item one</li>  
	<li>list item two</li>  
	<li>list item three</li>  
	<li>list item four</li>  
	<li>list item five</li>  
</ol>
```

理想的显示效果：  

![倒序列表项序号](/assets/2011/12/reversed-list.jpg)

  
可惜， reversed 目前还不被任何浏览器所[支持][4]。  
  
故，现阶段我们可以使用 js 给每一个 li 添加 value 的模式来模拟实现，这里有 Louis 提供的一个 示例： [http://jsfiddle.net/ImpressiveWebs/h4JcL/][5]  
  
**2013/01/30更新：**  
目前 Friefox 18+ 与 Chrome  已经支持有序列表序号的 reversed ：  
  
  


[1]: http://www.impressivewebs.com/reverse-ordered-lists-html5/
[2]: http://cdn.impressivewebs.com/2011-12/start-list.jpg
[3]: http://cdn.impressivewebs.com/2011-12/reversed-list.jpg
[4]: http://en.wikipedia.org/wiki/Comparison_of_layout_engines_(HTML5)#Attributes
[5]: http://jsfiddle.net/ImpressiveWebs/h4JcL/