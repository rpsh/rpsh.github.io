---
layout: post
title: 'CSS3: transition transform 学习笔记'
date: 2011-04-07 03:35
comments: true
header-img: "assets/common/css3-bg.jpg"
author:     "任平生"
tags:
    - CSS3
    - CSS
    - CSS/transition
    - CSS/transform
---

```
.box{
	-webkit-transition:background-color 2s ease-out; 
	-moz-transition:background-color 2s ease-out;
}
```
  

之所以将 transition 写在 `.box` 而不是 `.box:hover` 是因为当写在 `:hover` 中时， `transition-timing-function` 无法控制离开时的动画速度

  
```
transition-timing-function: [ liner | ease | ease-in | ease-out | ease-in-out 
| cubic-bezier(n,n,n,n) ]
```

  

- liner 匀速运动；

- ease 先慢后快再慢 【默认值】

- ease-in 先慢后快

- ease-out 先快后慢

- ease-in-out 先慢后平再慢

- cubic-bezier(n,n,n,n) 贝塞尔曲线 n 取值 0~1

via: [developer.mozilla.org/en/docs/Web/CSS/transition-timing-function][1] 

  

`transition` 目前在所有浏览器中都需要加前缀才能使用（`-webkit,-moz,-o`），ie9 目前尚不支持此属性

  
```
img:hover{
	-moz-transform:rotate(20deg) skew(30deg) translate(10px,10px) scale(2,1); 
	-moz-transform-origin:left center;
}
```

* rotate(deg) 旋转
* skew(x-deg, y-deg) 倾斜（变形）
* translate(x, y) 位移
* scale(x,y) 拉伸

其中如果(x,y) 只定义一个值的话，那么 x=y

  

  

* chrome 中 inline 元素不支持 transform
* ie9 支持 transform，需要 -ms 前缀
* ie9 中 inline 元素也可以使用transform

  
```
transform-origin:left center;
```

用于控制 `transform` 的原点位置，可以是诸如 `left` `right` 的值也可以是百分比或具体的`px`、`em`

  

  

**区分**

* `transition` 是过渡动画； 用来控制一些[CSS属性值改变][2]的快慢等

* `transform` 是变换；一般是形状的变化 or 位置的变化，可以类比Photoshop 中的 `Ctrl+T`，有拉伸、扭曲、变形、偏移

  

`transform` 与 `animation` 的区别是， `animation` 可以在 `keyframes`中详细地定义动画过程中的变换的参数，比如转动一半时间时  `scale(2)`，转动完成时 `scale(1)` 等

  

demo:  
[http://rpsh.net/demo/note/css3_transform.html][3]  
  

参考链接：

[http://www.w3.org/TR/css3-transitions/][4]

[http://www.w3.org/TR/css3-2d-transforms/][5]

[http://www.w3.org/TR/css3-3d-transforms/][6]

[http://www.w3.org/TR/css3-animations/][7]



[1]: https://developer.mozilla.org/en/docs/Web/CSS/transition-timing-function
[2]: https://developer.mozilla.org/en/CSS/CSS_transitions
[3]: http://rpsh.net/demo/note/css3_transform.html
[4]: http://www.w3.org/TR/css3-transitions/
[5]: http://www.w3.org/TR/css3-2d-transforms/
[6]: http://www.w3.org/TR/css3-3d-transforms/
[7]: http://www.w3.org/TR/css3-animations/