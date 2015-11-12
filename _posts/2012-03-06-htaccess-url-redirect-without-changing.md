---
layout: post
title: ".htaccess 重定向而URL地址不变"
description: "在做 liveto.me 时候就用了这个技巧， 使用 .htaccess rewrite 重定向内容，而地址栏的URL保持不变。 "
keyword: "htaccess"
date: 2012-03-06 08:07
comments: true
author:     "任平生"
header-img: "assets/common/apache-bg.jpg"
thumb-img: "assets/common/apache-thumb.jpg"
tags:
    - Apache
    - .htaccess
---


在做 liveto.me 时候就用了这个技巧， 使用 .htaccess rewrite 重定向内容，而地址栏的URL保持不变。  
  
只记得是加一个参数 P 即可，但这次用上后，发现无效，访问要重定向的网址会出现 404 错误。经过搜索发现是 Apache 的 mod_proxy 未启用所致。  
  
所以，只用在 httpd.conf 中 将 mod_proxy 相关项前的 # 去掉，然后重启 Apache 即可。  
  
  
```
RewriteEngine on  
RewriteCond %{HTTP_HOST} ^(www.)?tued\.net$ [NC]  
RewriteRule (.*) http://blog.tued.net/index [P,L]  
```
		  
参考链接：  
[http://www.zzxj.net/blog/fxs_2008/archive/2009/01/20/7.html][1]

[1]: http://www.zzxj.net/blog/fxs_2008/archive/2009/01/20/7.html