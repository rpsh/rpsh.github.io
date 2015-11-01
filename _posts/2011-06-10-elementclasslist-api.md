---
layout: post
title: 'HTML5: element.classList API'
date: 2011-06-10 09:31
comments: true
author:     "任平生"
header-img: "assets/common/js-bg.jpg"
tags:
    - JS
    - JS/classList
---


`element.classList` 将会返回 element 的 class 信息  
 

```js
{  
	length: {number},  
	add: function(){},  
	remove: function(){},  
	toogle: function(){},  
	item: function(){},  
	contanis: function(){}  
}  
```

```html
<div class="c1 c2 c3" id="ele"></div>  
```

```js
var ele =document.getElementById('ele');  
```

```js
ele.classList.add('c4');  
ele.classList.remove('c2');  
ele.classList.toggle('c3'); //移除 c3  
ele.classList.toggle('c3'); //添加 c3  
ele.classList.contains('c1') // true  
ele.classList.contains('c5') // false    
ele.classList.contains.itme(0) // c1  
```

使用 toggle 时候，如果class不存在，则增加这个class  
  
检测浏览器是否支持 `classList`:  

```js
'classList' in document.createElement('a') // true 为支持  
```
  
浏览器支持状况：  
Chrome 8+, Firefox 3.6+, Opera 11.5+ , IE 和 Safria 不支持  
  
  
参考链接：  
[http://davidwalsh.name/classlist][1]  
[https://developer.mozilla.org/en/DOM/element.classList][2]



[1]: http://davidwalsh.name/classlist
[2]: https://developer.mozilla.org/en/DOM/element.classList