---
layout: post
title: "GoAgentX ＋ Proxifier 让不支持代理的软件实现走代理"
description: "使用 Proxifier 可以为 Mac 上不支持设置代理的软件设置走代理的方式。"
keyword: "GoAgentX, Proxifier, Shadowsocks, 代理"
date: 2014-10-20 05:01
comments: true
header-img: "assets/common/greatwall-bg.jpg"
thumb-img: "assets/common/greatwall-thumb.jpg"
author:     "任平生"
tags:
    - GoAgentX
    - Shadowsocks
    - Proxifier
    - 代理
---
公司内上网必须要通过 HTTP 代理，而我们个人翻墙的时候用到的利器 GoAgentX 必须也要通过 http 代理才能连上 Shadowsocks 的代理服务器（这是多么的蛋疼）。

这时候，我们需要一个叫做 [Proxifier](http://www.proxifier.com/)（[网盘下载](http://pan.baidu.com/s/1pJkFybh)）的应用来实现那些不能设置代理的软件来通过代理。

1、在 Proxifier 里添加 HTTPS 代理

![Proxifier-http-proxy.png](http://note.rpsh.net/assets/2014/10/Proxifier-http-proxy.png)

![Proxifier-add-proxy.png](http://note.rpsh.net/assets/2014/10/Proxifier-add-proxy.png)



2、Rules 添加 GoAgentX 通过代理。  `GoAgentX;ss-local`
![Proxifier-add-rule.png](http://note.rpsh.net/assets/2014/10/Proxifier-add-rule.png)

![Proxifier-goagentx.png](http://note.rpsh.net/assets/2014/10/Proxifier-goagentx.png)



3、大功告成。


其他一些不能设置代理的应用亦可如法炮制。
如：

```
"Alfred 2"; idea;Thunder*; iTerm; Terminal;php; Dropbox; Sparrow; "Sequel Pro"; python; ruby; wget; curl; GitHub; git-remote-https; java;npm; node; perl;prl*;itunes; sftp;java;Justinmind;plugin_*;ascp;"Application;Loader";geny*;Vbox*;whois;traceroute;stroke;ssh;ALiWangwang;MacUpdate*;git*;Git;fzs*;mail;flickr*;xulr*;imess*;com.apple.im*;Airmail;Adium;Prot*;Tokens;Ali*;Lite*;file*;ssh;ftp;Adobe*;PDApp*;Creative*;Vbox*;xulrunner;Virtual*;PDApp;Bit*;Domainers;fire*;plugin*;Atom*;Tokens;.com.realmacsoftware*;Xcode;java;httpd;qboxrsctl;Wunderlist;"Mark Man";
```

