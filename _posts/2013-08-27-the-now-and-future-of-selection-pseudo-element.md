---
layout: post
title: "伪元素 ::selection 的现状与未来"
description: "伪元素 `::selection` 用来定义反选的样式"
keyword: "selection, css"
date: 2013-08-27 03:01
comments: true
author:     "任平生"
header-img: "assets/common/css-bg.jpg"
thumb-img: "assets/common/css-thumb.jpg"
tags:
    - CSS
    - CSS/selection
---
伪元素 `::selection` 用来定义反选的样式，一般写法如下：  

```css
::-moz-selection{  
	color: white;  
	background: hotpink;  
}  
::selection{  
	color: white;  
	background: hotpink;  
} 
```
  
除了 IE6-8，其他现代浏览均支持这段CSS。Firefox 是唯一一个需要 `-moz` 前缀的浏览器。请注意，若为了缩减代码，而将  `::-moz-selection` 与 `::selection` 通过逗号连写在一起是无法生效的。  
 
```css
::-moz-selection, 
::selection{  
	color: white;  
	background: hotpink;  
}
/* 注意：这段CSS是无效的 */  
``` 
  
虽然 `::selection` 被广泛地应用，但它却不属于W3C规范的一部分。  
  

## W3C规范的说法

查阅 [W3C selectors module](http://www.w3.org/TR/css3-selectors/#selection), level3 ，只留下一句：  
  

> This section intentionally left blank. (This section previously defined a ::selection 
> pseudo-element.)   

> _本节特意留空（本节曾经用来定义伪元素::selection）_

_/* 尼玛，这是行为艺术啊  */_  
  
就像 MDN 文档中醒目标明的那样，这是一个『不标准』的特性。  
  
  

## 为什么规范里没有 ::selection

   
MDN 的[文档](https://developer.mozilla.org/en-US/docs/Web/CSS/::selection)提供了一个比 W3C 的规范文档要详尽一些的原因解释这个事情：  
  

> Though this pseudo-element was in drafts of CSS Selectors Level 3, it was removed 
> during the Candidate Recommendation phase, as it appeared that its behavior 
> was under-specified, especially with nested elements, and interoperability 
> wasn't achieved. 

> 这个伪元素是 CSS3 选择器草案的一部分，不过在候选推荐方案中被剔除。因为在嵌套元素中，根据 ::selection 的指定会出现一些互操作性的问题。（注：最后这一句翻译可能不准确，求指正） 

不过，MDN 里提供了一个链接，指向 W3C 对这一问题讨论的[邮件列表](http://lists.w3.org/Archives/Public/www-style/2008Oct/0268.html "嵌套元素上 ::selection 是如何作用的")。

  

## ::selection 的其他一些身影

- [CSS Selectors level 4](http://dev.w3.org/csswg/selectors4/ "CSS Selectors level 4") 草案中没有 `::selection` 的章节，前景不妙；
- 2012年1月的[一个讨论](http://lists.w3.org/Archives/Public/www-style/2012Jan/0514.html "Status of the ::selection pseudo-element")：为什么将 `::selection` 从规范中删除，提出了一个替代语法方案，但未获得任何关注；
- [CSS3 UI 模型](http://www.w3.org/TR/css3-ui/ "CSS3 UI 模型")中的[伪元素](http://www.w3.org/TR/css3-ui/#pseudo-elements "伪元素")章节也[提到](http://www.w3.org/TR/css3-ui/#changes-list)了 `::selection` 从规范中删除的事情；
- 在写这篇文章时， `::selection`  依然包含在 HTML5 Boilerpalte 的 main.css 中；
- 针对上一条，H5BP 的作者 Paul Irish [回应](https://github.com/h5bp/html5-boilerplate/issues/1077)说，『H5BP 是前端开发中的一个实例应用，W3C 规范中的状态对这个项目特性的增删的影响甚微』
  


## 使用 ::selection 时的一些 Tips
尽管 `::selection` 的未来岌岌可危，但依然有很多人喜欢它。当然也有一些人认为它搞乱了浏览器应当独立控制的一些东西。不过，还是有一些 Tips 值得我们了解：

- `::selection` 可以使用的属性有： `color`，`background`，`background-color`，`text-shadow`；

- 虽然 `background` 可以使用，但 `background-image` 却是不能使用的；

- 因为 `::selection` 并不是标准的伪元素和无望进入规范的前景， Firefox 可能永远不会支持无 `-moz` 前缀的语法；

- `::selection` 必须使用双冒号，因为 CSS3 规范中要求所有新增的伪元素都必须使用双冒号的语法结构，这是为了跟伪类区分开来（伪类使用单冒号，如：`a:hover`）。
  
  
  
## 结论
如果喜欢 `::selection`，就大胆的用吧。若有一天浏览器不再支持这个伪元素了，也不要有任何的惊讶。

     
原文： [What’s the Status of the ::selection Pseudo-element?](http://www.impressivewebs.com/status-selection-pseudo-element/)