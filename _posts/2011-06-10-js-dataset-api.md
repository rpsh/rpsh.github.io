---
layout: post
title: "HTML5: element.dataset API"
description: "Firefox 6 中将增加一个新的 API： element.dataset 用来获取自定义数据属性 data-* 设置的值。"
keyword: "dataset, js"
date: 2011-06-10 08:28
comments: true
author:     "任平生"
header-img: "assets/common/js-bg.jpg"
thumb-img: "assets/common/js-thumb.jpg"
tags:
    - JS
    - JS/dataset
---


Firefox 6 中将增加一个新的 API： `element.dataset` 用来获取自定义数据属性 data-* 设置的值。  
如果使用这个 element.dataset，那么 data-* 的命名需要有以下几点注意：  
  

* 名字不能以 xml 开头
* 名字中不能使用分号
* 名字中不能包含大写字母 A-Z

  
  
自定义数据属性将遵循以下规则转化为 DOMStringMap 键值：  
  

* 中划线 - 将被移除；
* 跟着 - 的所有字母将被转化为大写（即驼峰命名）

  
  
代码：  
```
<div id="myDiv" data-name="myDiv" data-id="myId" data-my-custom-key="This is the value"></div>  
```

```
var ele = document.getElementById('myDiv');  
ele.dataset.id  // myId  
ele.dataset.myCustom.Key // This is the value  
ele.dataset.newKey = 'rpsh' // 将会增加 data-new-key="rpsh"  
```

```
<div id="myDiv" data-name="myDiv" data-id="myId" data-my-custom-key="This is the value" data-new-key="rpsh"></div>  
```

  
注：Chrome 8.0, Opera 11.1, Safari 6 已经支持该 API。IE 尚无版本支持  
  
参考链接：  
[http://davidwalsh.name/element-dataset][1]  
[https://developer.mozilla.org/en/DOM/element.dataset][2]

[1]: http://feedproxy.google.com/~r/Bludice/~3/645gxzBK16U/element-dataset
[2]: https://developer.mozilla.org/en/DOM/element.dataset