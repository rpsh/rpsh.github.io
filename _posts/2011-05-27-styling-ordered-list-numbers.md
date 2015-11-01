---
layout: post
title: '自定义有序列表 li 项目符号的数字样式'
date: 2011-05-27 09:07
comments: true
categories: 

tags:
    - CSS
---


下面是一个自定义有序列表 li 项目符号样式的思路：  
  
<ol>  
 <li>List item one</li>  
 <li>List item two</li>  
 <li>List item three</li>  
 <li>List item four</li>  
</ol>  
  
  
CSS:  
  
```css
ol{  
	margin-left:0px;  
	padding-left:0px;  
	counter-reset:li;  
}  
```

```css
ol > li{
	position:relative;
	margin:0 0 6px 2em;
	list-style:none;
}
```


```css
ol >li:before{
	content:counter(li);
	counter-increment:li;
	position:absolute;
	color:red;
}
```
  

实现关键点就是 ol 的 `counter-reset:li` ，和使用 `before` 伪元素的 `count:counter(li)` 和 `counter-increment:li` 来实现添加出递增数字。

然后，就可以随意定义 before 伪元素的样式了

  

参考链接： [http://www.456bereastreet.com/archive/201105/styling_ordered_list_numbers/][1] 



[1]: http://www.456bereastreet.com/archive/201105/styling_ordered_list_numbers/