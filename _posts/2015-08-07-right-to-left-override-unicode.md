---
layout: post
title: '让文字从右往左反转显示的 unicode'
description: "有一个特殊的 unicode 可以让跟在它后边的文字从右往左反转显示，利用它可以做一些有趣的事情，让一些看起来正常的文字，其实背后藏着一些不正常的原文。"
keyword: "unicode, 有趣的unicode"
date: 2015-08-07 03:30
comments: true
author:     "任平生"
tags:
    - unicode
    - 趣识
---
有一个特殊的 unicode 可以让跟在它后边的文字从右往左反转显示


```
&#8238; 日照香炉生紫烟
```  

效果：
<div>
		&#8238; 日照香炉生紫烟
</div>


利用它可以做一些有趣的事情，让一些看起来正常的文字，其实背后藏着一些不正常的原文。

<table>
	<thead>
		<tr>
			<th></th>
			<th style="text-align: center">code</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>html 实体</td>
			<td style="text-align: center">&amp;#8238;</td>
		</tr>
		<tr>
			<td>html 实体</td>
			<td style="text-align: center">&amp;#x202e;</td>
		</tr>
		<tr>
			<td>C/C++</td>
			<td style="text-align: center">\u202E</td>
		</tr>
	</tbody>
</table>



参考资料：

* [http://www.fileformat.info/info/unicode/char/202e/index.htm](http://www.fileformat.info/info/unicode/char/202e/index.htm)
* [http://krebsonsecurity.com/2011/09/right-to-left-override-aids-email-attacks/](http://krebsonsecurity.com/2011/09/right-to-left-override-aids-email-attacks/)