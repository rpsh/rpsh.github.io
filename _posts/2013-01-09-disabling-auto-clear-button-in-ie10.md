---
layout: post
title: '移除 IE10 input 输入框上的清除按钮'
date: 2013-01-09 08:19
comments: true
header-img: "assets/common/ie-bg.jpg"
author:     "任平生"
tags:
    - CSS
    - IE
---


![ie input clear](/assets/2013/01/ie10_clear_button.png)

  
IE10 除了默认交互控件的 UI 丑之外，还给 input 加了一个清除按钮，虽然看起来很有用的样子，实际情况中却有很多设计容不下它，所以我们前端就要隐藏掉这个东西，方法：  

```css
input[type=text]::-ms-clear {  
	display: none;  
}
```

资料：  
[http://msdn.microsoft.com/en-us/library/windows/apps/hh465740.aspx ][3]  
  


[1]: http://2.bp.blogspot.com/-FDHzeyX3AsE/UO0nDiuaigI/AAAAAAAAHs0/Lgyq5u40oFg/s320/ie10_clear_button.png
[2]: http://2.bp.blogspot.com/-FDHzeyX3AsE/UO0nDiuaigI/AAAAAAAAHs0/Lgyq5u40oFg/s1600/ie10_clear_button.png
[3]: http://msdn.microsoft.com/en-us/library/windows/apps/hh465740.aspx