---
layout: post
title: '给网址最后添加斜杠'
date: 2013-11-20 09:05
comments: true
author:     "任平生"
tags:
    - 性能优化
---

如果可能，应尽量给 URL 的最后加上一个斜杠 /
比如我们在浏览器里打开 `http://v.qq.com/tv` , 会先 301 重定向到 `http://v.qq.com/tv/` 然后才开始请求页面内容资源

![url_slash.png](/assets/2013/11/url_slash.png)

这样不仅白白耗费一次服务器请求响应，而且让页面响应时间慢了 146 毫秒 (以截图为例)。此外，不一致的 URL 也不利于 SEO。

原因：

* `http://v.qq.com/tv/` 浏览器的请求发送到服务器后，服务器会直接返回 `tv/` 目录的默认首页（如：index.html）；
* `http://v.qq.com/tv` 服务器接收到这个请求后，会先搜索根目录下是否有 `tv` 这个文件，如果没有，就会把 `tv` 当成目录处理，然后返回 `tv/` 下的默认首页


参考资料：

[http://blogs.msdn.com/b/ie/archive/2005/04/11/407189.aspx](http://blogs.msdn.com/b/ie/archive/2005/04/11/407189.aspx)