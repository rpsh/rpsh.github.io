---
layout: post
title: "javascript keycodes 键盘键值"
description: "在页面上增加键盘快捷键"
keyword: "keycodes, js"
date: 2011-06-08 09:59
comments: true
header-img: "assets/common/js-bg.jpg"
thumb-img: "assets/common/js-thumb.jpg"
author:     "任平生"
tags:
    - JS
    - Keyboard
---

![键盘](http://note.rpsh.net/assets/2011/05/keycodes.png)
via：[http://shikargar.wordpress.com/2010/10/27/javascript-key-codes/][1] 


在页面上增加键盘快捷键：  
  
```
var inputFocus = false;  
$(':input').blur(function(){  
	inputFocus = false;  
});  
$(':input').focus(function(){  
	inputFocus = true;  
});  
$(document).keydown(function(e){  
	if(!inputFocus){  
		if(e.which == 87 && !e.ctrlKey){  
			//do something  
			return false;  
		}  
	}  
});
```

[1]: http://shikargar.wordpress.com/2010/10/27/javascript-key-codes/