---
layout: post
title: 'window.history'
date: 2011-05-18 10:18
comments: true
categories: 
tags:
    - JS
    - JS/history
---


通常，我们使用 #hash 跳转页面的某个位置，但有时跳转并不是你想要的，如果阻止了默认的跳转行为，那么 #hash 就不会计入 history ，点击浏览器的后退按钮就什么都不会发生了 （想象 gmail 中的所有操作都是靠 #hash 来切换不同的界面的，而且点后退按钮可以返回之前操作的界面）  
  
通过 HTML5 的 history API，我们可以很容易地实现我们想要的：  
  
```
history.pushState(data, title [,url])  
history.replaceState(data, title, [,url])  
```

```
if( history.pushState){  
	history.pushState(null, null, '#myhash');  
}else{  
	location.hash = '#myhash';  
}  
```

浏览器支持：  
  

* firefox 4+
* safari 5+
* chrome 8+

  
  
history.pushState() 来改 hash 是个杀鸡用牛刀的耍酷，更帅的应用场景可以看这个视频：  
[http://blip.tv/play/AYKSzQUC][1]  
  
当点击链接切换页面的时候，阻止默认的跳转到新页面的行为，而通过ajax来加载页面上不同区域的内容，并且此时地址栏的 URL 也做相应的改变！更酷的是后退按钮也可以很好地工作！ 这大大缩短了加载整个页面所需的时间。  
  
实现代码：  
  
```
$('#slider a').click(function() {  
	history.pushState({ path: this.path }, '', this.href)  
	$.get(this.href, function(data) {  
		$('#slider').slideTo(data)       
	})  
	return false   
})
```
  
  
当点击后退按钮时， 会触发 onpopstate ：  

```
$(window).bind('popstate', function() {  
	$('#slider').slideTo(location.pathname)  
})  
``` 
  
  
参考资料：  
[http://lea.verou.me/2011/05/change-url-hash-without-page-jump/][2]  
[http://css-tricks.com/hash-tag-links-padding/][3]  
[http://www.w3.org/TR/html5/history.html#the-history-interface][4]  
[https://developer.mozilla.org/en/DOM/Manipulating_the_browser_history][5]

[1]: http://blip.tv/play/AYKSzQUC
[2]: http://lea.verou.me/2011/05/change-url-hash-without-page-jump/
[3]: http://css-tricks.com/hash-tag-links-padding/
[4]: http://www.w3.org/TR/html5/history.html#the-history-interface
[5]: https://developer.mozilla.org/en/DOM/Manipulating_the_browser_history