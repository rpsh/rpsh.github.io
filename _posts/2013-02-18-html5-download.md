---
layout: post
title: "HTML5 download 属性"
description: "HTML5 的 download 属性有两个作用：一、使链接点击后发起下载，二、通过download 属性来定义下载文件的名字"
keyword: "download"
date: 2013-02-18 14:28
comments: true
author:     "任平生"
header-img: "assets/common/html5-bg.jpg"
thumb-img: "assets/common/html5-thumb.jpg"
tags:
    - HTML5
    - HTML5/download
---
HTML5 的 download 属性有两个作用：  
  
一、使链接点击后发起下载  
代码一：  

```html
<a href="/files/logo.png" download="mylogo">My Site</a>	
```

通常点击这么一个链接，浏览器会直接打开 logo.png 的图片（png 是浏览器支持直接打开的文件类型）。  
而支持 download 属性的浏览器里点击这个链接，会下载这张图片到本地，并命名为 mylogo.png  
  
  
二、通过download 属性来定义下载文件的名字：  
代码二：  

```html
<a href="/files/adlafjlxjewfasd89asd8f.zip" download="expenses">Download Zip</a> 
```

点击后会开始下载得到文件 adlafjlxjewfasd89asd8f.zip ，而通过 HTML5 的 download 属性，下载得到的文件名字是 expenses.zip 。  
  
示例：  

1. [http://html5-demos.appspot.com/static/a.download.html](http://html5-demos.appspot.com/static/a.download.html)

2. [http://davidwalsh.name/demo/html5-download.php](http://davidwalsh.name/demo/html5-download.php)
  
目前只有 Chrome 支持 download 属性。  
       
  
最后还发现个奇技淫巧：  
代码三：  
```html
<a download="test.txt" href="data:text/plain;base64,SGVsbG8gV29ybGQh">Hello World</a>
```

示例： [Hello World](data:text/plain;base64,SGVsbG8gV29ybGQh) 
[支持](http://javascript-reverse.tumblr.com/post/37056936789/html5-download-attribute#dsq-comment-body-726105808)  [dataURI](http://jsfiddle.net/MNFes/) ，是不是太逆天了，哈哈


参考资料：  
[http://updates.html5rocks.com/2011/08/Downloading-resources-in-HTML5-a-download](http://updates.html5rocks.com/2011/08/Downloading-resources-in-HTML5-a-download) 
[http://davidwalsh.name/download-attribute](http://davidwalsh.name/download-attribute)