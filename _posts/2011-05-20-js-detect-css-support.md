---
layout: post
title: '判断浏览器是否支持某个css属性'
date: 2011-05-20 10:14
comments: true
categories: 
tags:
    - JS
    - 浏览器
---


根据 UA 来判断浏览器版本，再根据浏览器版本来确定是否支持某个 css 属性的方法弱爆了，直接判断浏览器是否支持某个CSS属性才是王道。  
  
判断是否支持 `text-overflow`

```  
if( 'textOverflow' in document.documentElement.style){  
	alert('support');  
}else{  
	alert('no support');  
}
```
  
判断是否支持 `text-shadow`  
  
```
if( 'textShdow' in document.documentElement.style){
	alert('support');
}else{
	alert('no support');  
}
```

从上可以看出，CSS属性，采用首字母小写的驼峰命名法。

  

一些 CSS3 属性需要有浏览器厂商前缀，对于这些属性的判断方法：

  

判断是否支持 `transform`

```
if( 'MozTransform' in document.documentElement.style || 'WebkitTransform' in 
document.documentElement.style || 'OTransform' in document.documentElement.style 
|| 'msTransform' in document.documentElement.style){
	alert('support');  
}else{
	alert('no support');
}
```
  

我们可以注意到，除IE外，各个浏览器使用首字母大写的厂商前缀的开头，IE则用小写的 `ms` 开头。

如果不知道某个CSS属性在 DOM 中的名字，可以在下面这些网址查找

IE: [http://msdn.microsoft.com/en-us/library/ms533055(v=VS.85).aspx][1]  
Firefox: [https://developer.mozilla.org/en/DOM:CSS][2]  
Opera: [http://www.opera.com/docs/specs/opera8/js/dom/css/][3] 



[1]: http://msdn.microsoft.com/en-us/library/ms533055(v=VS.85).aspx
[2]: https://developer.mozilla.org/en/DOM:CSS
[3]: http://www.opera.com/docs/specs/opera8/js/dom/css/