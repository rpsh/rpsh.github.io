---
layout: post
title: 'IE 中按后退按钮页面乱码的解决方案'
date: 2012-01-11 10:40
comments: true
header-img: "assets/common/ie-bg.jpg"
author:     "任平生"
tags:
    - IE
    - JS
---


今天遇到一个问题，退出登录后，点IE浏览器的后退按钮，页面出现了乱码，查看页面编码变成了 GB2312。  
找了一圈也没找到问题所在。不过找到一个类似的解决办法，就是判断当前页面编码是否为 utf8，如果不是，则刷新页面。  
代码：  
  

```javascript
<script type="text/javascript">  
	try{  
		if ((document.characterSet || document.charset).toLowerCase() != 'utf-8' && navigator.userAgent.indexOf("MSIE")>0){  
			window.location = window.location;  
		}  
	}  
	catch (exp) {}
</script>
```

