---
layout: post
title: '一些神奇的 IE Meta Tags'
date: 2013-01-21 15:41
comments: true
header-img: "assets/common/ie-bg.jpg"
author:     "任平生"
tags:
    - IE
    - HTML/Meta
    - 趣识
---

```html
<meta name="MSSmartTagsPreventParsing" content="true" />  
```

作用：禁用 IE6 的 Smart Tags 功能。  
详解：微软在 IE6 Beta 版和 Word 2010 中引入了一个功能：[Smart Tags][1]，自动给一些「标签」词语加上带下划线样式的链接，鼠标hover时候可以使用预定义的一些程序的功能：  

![Smart Tags](/assets/2013/01/Smarttags.png)

（图片来自 [wikipedia][3]）

  
一般这些链接程序都是指向微软或其附属公司的业务。显而易见，引起的[轩然大波][4]最终让微软在正式版 XP 「也就是正式版本的 IE6 」中移除这个功能。不过这个功能最后在 IE8 中借尸还魂了，就是所谓的[加速器][5]「Accelerators」。 
  
  
不过 XP 用户可以下载一个 Smart Tags for the Everyday Web 的程序，Smart Tags 功能就可以登堂入室入驻 XP 中了。 但是在我 7 年的网络使用经历中，在写这篇笔记之前我还真不知道有这个东西，更没见过也没在其他人的电脑上见过这个东西。所以，我们华丽滴无视它吧，加这个 Meta Tag 纯属增加无用字节浪费流量的蛋疼行为。  
  

```html
<meta http-equiv="imagetoolbar" content="no" />
```

作用：禁用 IE6 中的图片快速保存工具条  
详解：又是 IE6 中的一个特性，鼠标 hover 到一个尺寸大于200x200的图片上会出现一个快速功能操作工具条，提供注入保存、打印、发送邮件等功能。此特性[只有 IE6 支持][6]。 

![ie6 image toolbar](/assets/2013/01/image-toolbar-example.jpg)


图片来自 [ma.tt][9]

如果只是禁用页面上某个图片的 imagetoolbar ，可以使用 [galleryimg="no"][10] 属性：

```html 
<img src="mypicture.png" galleryimg="no">  
```



```html
<meta http-equiv="msthemecompatible" content="no" />  
```

作用：禁用 input textarea select 等控件的默认样式  
详解：XP 中微软引入了一套新的主题样式，这套主题样式会连带修改网页中的一些诸如输入框、下拉框的样式，通过 msthemecompatible 可以[禁用此样式][11]，恢复至 win2K 时的样式。  
  
```html
<meta http-equiv="cleartype" content="on" />  
```
作用：在 Mobile IE 上开启文字的 [Clear Type][12] 效果。对 PC 上的 IE 无任何作用。  
详解：无。 关于如何禁用 PC 上的 ClearType ，有一个绕道的[方法][13]：IE 会禁用使用滤镜元素的 ClearType，所以可以使用以下代码来禁用 ClearType 。 

```css 
#target{  
	filter:Alpha(opacity=99);  
}
```
  
  
  


[1]: http://searchwinit.techtarget.com/definition/Smart-Tags
[2]: http://upload.wikimedia.org/wikipedia/en/9/9e/Smarttags.PNG
[3]: http://en.wikipedia.org/wiki/Smart_tag_%28Microsoft%29
[4]: http://www.yesky.com/8/184008.shtml
[5]: http://msdn.microsoft.com/en-us/library/cc289775(v=vs.85).aspx
[6]: http://msdn.microsoft.com/zh-cn/library/ms532986(v=vs.85).aspx
[7]: http://4.bp.blogspot.com/-PnfYPcCjYg8/UP1YhVlmhtI/AAAAAAAAHtQ/nuC0Rl7TFiU/s400/image-toolbar-example.jpeg
[8]: http://4.bp.blogspot.com/-PnfYPcCjYg8/UP1YhVlmhtI/AAAAAAAAHtQ/nuC0Rl7TFiU/s1600/image-toolbar-example.jpeg
[9]: http://ma.tt/2004/07/image-toolbar/
[10]: http://msdn.microsoft.com/zh-cn/library/ms533774(v=VS.85).aspx
[11]: http://msdn.microsoft.com/zh-cn/library/ms533689(v=vs.85).aspx
[12]: http://zh.wikipedia.org/wiki/ClearType
[13]: http://stackoverflow.com/questions/1031531/ie8-disable-cleartype