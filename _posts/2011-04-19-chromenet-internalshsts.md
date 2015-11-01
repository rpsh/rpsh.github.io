---
layout: post
title: '设置 Chrome 强制网站使用 HTTPS'
date: 2011-04-19 08:19
comments: true
header-img: "assets/common/chrome-bg.jpg"
author:     "任平生"
tags:
    - Chrome
    - https
---

[chrome://net-internals/#hsts][1]  
可以设置强制使用 https 链接的网址  


```
(chrome|checkout|health|docs|spreadsheets|sites|appengine|encrypted).google.com  
```

  
参考链接：  
[http://dev.chromium.org/sts][2]  
[http://src.chromium.org/viewvc/chrome/trunk/src/net/base/transport_security_state.cc?view=log][3]

[1]: chrome://net-internals/#hsts
[2]: http://dev.chromium.org/sts
[3]: http://src.chromium.org/viewvc/chrome/trunk/src/net/base/transport_security_state.cc?view=log