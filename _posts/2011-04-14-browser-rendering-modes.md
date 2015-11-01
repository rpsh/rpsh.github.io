---
layout: post
title: '浏览器渲染模式'
date: 2011-04-14 08:44
comments: true
author:     "任平生"
tags:
    - 浏览器
    - 渲染模式
---


共有三种渲染模式：怪异模式（Quirks mode）、准标准模式（almost standards mode）、标准模式（full standards mode）  
各个浏览器相同版本的 标准模式 和 准标准模式 之间差异极少。  
  

![浏览器渲染模式差异](/assets/2011/04/browser_compat.png)
via: [http://www.w3help.org/zh-cn/causes/readme.html][1] 
  
`<!doctype html>`

当页面上有文档声明（DOCTYPE declaration）时，页面就会进入标准模式渲染页面。  
  
HTML4.01 规范中提到，DTD签名或后面容许出现空白符，这里提到的“空白符”包括 空格符、换行符、制表符和注释。  
实际情境中，在DTD前边前加入注释或其他内容，在某些浏览器中 DTD 将无法识别，从而进入怪异模式。  
  
![文档声明](/assets/2011/04/DTD.png)
via: [http://www.w3help.org/zh-cn/causes/HG8001][2] 
  
所以，**请确保 DTD 之前没有其他字符，即便有，也只能是 空格符、换行符和制表符。**  
  
在 ie 下，只使用 `<!doctype` 就能触发浏览器的标准模式，很神奇。推测 ie 可能是判读如果以 `<!doctype` 开头的话，开发者就是想进入标准模式，于是 ie 就无视了后边的信息，直接进入标准模式渲染了  
  
在怪异模式下，ie 盒模型的 CSS中定义的宽度 width 是包括了 padding border 值。 使用 `clientWidth` 得出的值 = `width - paddingLeft - paddingRight - borderLeft - borderRight`  
  
而非ie浏览器，`clientWidth/clientHeight` 的计算方式在怪异模式跟标准模式相同。  
  
![默认盒模型](/assets/2011/04/box_mode.png)

  
  

* IMG 元素在 IE6(Q) IE7(Q) IE8(Q) 下无法设置 `padding`，其值永远为 0。也就是说，IMG 元素的盒模型在这些浏览器中，其 padding box 与其 content box 是重合的。
* 和 TABLE 元素一样，目前所有的主流浏览器也都认为 `HR/BUTTON/INPUT[type=button/submit/reset]` 元素的内容区域是由 border box 决定的，因此在这些元素上设置的 `width` 和 `height` 将作用在这些元素的 border box 上。
* IFRAME 元素在 IE6(S) 下有一个 Bug，该元素实际使用的 `padding-right` 和 `padding-bottom` 的值将分别多出其 `border-right-width` 和 `border-bottom-width` 的值的 2 倍。
* INPUT[type=text]/TEXTAREA 元素设置 `width`、`height` 时，它们在所有浏览器的怪异模式 (Q) 中都被作用到了 border box，而在所有浏览器的标准模式 (S) 中则作用到了 content box。

  
一些常见的 doctype 及会触发的模式  

[![盒模型](/assets/2011/04/doctype.png)][3]

  
  
参考链接

* [http://www.w3help.org/zh-cn/causes/readme.html][1]  
* [http://www.w3help.org/zh-cn/kb/001][4]  
* [http://msdn.microsoft.com/en-us/library/bb250395.aspx][5]

[1]: http://www.w3help.org/zh-cn/causes/readme.html
[2]: http://www.w3help.org/zh-cn/causes/HG8001
[3]: /assets/2011/04/doctype.png
[4]: http://www.w3help.org/zh-cn/kb/001
[5]: http://msdn.microsoft.com/en-us/library/bb250395.aspx