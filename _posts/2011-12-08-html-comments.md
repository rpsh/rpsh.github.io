---
layout: post
title: 'HTML 注释的前世今生'
date: 2011-12-08 07:50
comments: true
header-img: "assets/common/html-bg.jpg"
author:     "任平生"
tags:
    - HTML
    - 注释
    - 趣识
---


HTML 语言是从 SGML 衍生来的，HTML 的「注释」语法也就应该跟 SGML 的「注释」是一致的。实际上，它们之间却有一些的差异。  
  
SGML 是这样定义「注释」的：  

> 「注释」以 `<!` 开始，以 `>` 结束，中间可以有零个或多个注释块。每个「注释块」以 `--` 开始，并以 `--` 结束，并且其中不能包含 `--` 
> 。

  
下面是一些合法的 SGML 「注释」:  

* `<!-- Hello -->`
* `<!-- Hello -- -- Hello-->`
* `<!---->`
* `<!------ Hello -->`
* `<!>`

我们可以看到，注释可以为空，只有对称的两个 -- 。同样，<!>也是合法的，它不包含任何「注释块」。  
  
`<!------> hello-->` 按照 SGML 是合法的，但却不是一个合法的 HTML 注释。这条注释包含了两个「注释块」，其一为： `----` ；其二为： `--> hello--`； 它们都被 -- 包裹，所以是合法的 SGML 注释。而如果用浏览器查看，会显示出 `hello--> `。  
  
  
我们再来看一下 W3C 对 「HTML 注释」的定义。  
在 HTML4.01 中[定义][1]如下：  

> 「注释标记」的以 `<!` 开始，以 `>` 作为结束，注释内容以 `--` 开始，以 `--` 结束。`<!--` 之间不能有空格，而 `-->` 
> 之间可以有空格。

可能是为了遵循 SGML 对注释的定义，W3C给出了这么一个纠结的说法。并提醒网页制作者避免在注释内容中出现两个或两个以上的连字符(`-`) 。对了，W3C 不忘强调 「注释」 是一个标记（Note that comments are markup）。  
  
而在 HTML5 中，W3C 清晰地给出了注释的[语法][2]：  

> 「注释」必须以四个连续的字符： `<!--` 开始，以三个连续的字符 `-->` 结束。注释内容不能以小于号 `>` 或者连字符加大于号 `->` 开始；注释内容中间部分不能包含两个连续的连字符(`--`)，注释内容不能以连字符(`-`)作为结束。 


  
一些实际测试结果：  

1.   
`<!hello world>` 所有浏览器都会将其解析为注释；（天哪，两个连字符竟然不是必须的！） 
2.  `<!-hello world>` 所有浏览器都会将其解析为注释； 
3.  `<!--hello world>` IE会将其识别为一个注释，其后的内容可以显示。其他浏览器（Firefox、Chrome、Opera）则会将这条注释后边的所有内容都视为注释内容而不显示出来。
4. `<!-- -- helo world>` 结论同上。
5. `<!-- hello world> rpsh.net <!--  -->` 或者 `<!-- -- hello world> rpsh.net <!--  -->`  在所有浏览器中 rpsh.net 都不会显示出来
6. `<!-- -- --> rpsh.net <!-- -- -->` 或者 `<!-----> rpsh.net <!----->` 在所有浏览器中 rpsh.net 都可以显示出来。
7. `<!---> rpsh.net <!--->` 在 Opera 中 rpsh.net 不会显示，其他浏览器中rpsh.net 都可以显示。
8. `<!-- <! rpsh.net -->` 所有浏览器都将其解析为一条注释，其后的内容可以正常显示。
9. `<!-- -- > rpsh.net -->` Opear 中会显示出 `rpsh.net -->`，其他浏览器都将其解释为一条注释，其后的内容正常显示。
10. `<!-- > rpsh.net -->` 所有浏览器都将其解析为一条注释，其后的内容可以正常显示。 
11. `<!-- hello world <!-- rpsh.net -->` 所有浏览器都将其解析为一条注释，其后的内容可以正常显示。 
12. `<!-- -->hello world<!-- >rpsh.net<!-- -->` 所有浏览器中 hello world 显示，rpsh.net不显示。

从这些实验结果，我们可以得出以下结论：  
  

* 对于所有浏览器 `<! >` 即可声明一条注释，注释内容不必用 `--` 包裹。
* 注释内容中一旦以 `--` 开始，则注释内容中就不应当出现 `-->`，否则将会视其为注释的结束标记。

  
  
  
  
参考链接：  
[http://htmlhelp.com/reference/wilbur/misc/comment.html][3]  
[http://www.w3.org/TR/html401/intro/sgmltut.html#h-3.2.4][4]  
[http://www.w3.org/TR/html5/syntax.html#comments][2]  
[http://www.howtocreate.co.uk/SGMLComments.html][5]

[1]: http://www.w3.org/TR/html4/intro/sgmltut.html#h-3.2.4
[2]: http://www.w3.org/TR/html5/syntax.html#comments
[3]: http://htmlhelp.com/reference/wilbur/misc/comment.html
[4]: http://www.w3.org/TR/html401/intro/sgmltut.html#h-3.2.4
[5]: http://www.howtocreate.co.uk/SGMLComments.html