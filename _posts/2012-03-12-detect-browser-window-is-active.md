---
layout: post
title: "JS 判断浏览器窗口是否处于当前激活状态"
description: "项目中有个定时器，希望在浏览器窗口处于激活状态时运行，而非激活状态则停止。代码如下："
keyword: "js"
date: 2012-03-12 09:46
comments: true
author:     "任平生"
header-img: "assets/common/js-bg.jpg"
thmb-img: "assets/common/js-thmb.jpg"
tags:
    - JS
---


项目中有个定时器，希望在浏览器窗口处于激活状态时运行，而非激活状态则停止。代码如下：  
  
```js
timer = setInterval(adds,800);  
  
function onBlur(){  
	clearInterval(timer);  
}  
function onFocus(){  
	clearInterval(timer);  
	timer = setInterval(adds,800);  
}  
  
// 判断浏览器窗口是否处于激活状态  
if(/*@cc_on!@*/false){  //对于 IE 要专门开小灶  
	document.onfocusin = onFocus;  
	document.onfocusout = onBlur;  
}else{  
	window.onfocus = onFocus;  
	window.onblur = onBlur;  
}  
```  
  
如果使用 jquery 的话，可以用代码：  

```js
$(window).blur(function(){  
	onBlur();  
});  
$(window).focus(function(){  
	onFocus();  
});  
```

不过 ie7，ie6 无效。  
  
via: [http://stackoverflow.com/questions/1060008/is-there-a-way-to-detect-if-a-browser-window-is-not-currently-active][1]  
  



[1]: http://stackoverflow.com/questions/1060008/is-there-a-way-to-detect-if-a-browser-window-is-not-currently-active