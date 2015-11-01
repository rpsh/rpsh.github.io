---
layout: post
title: '解决 Chrome 不能打开 iTunes 或 Mac Appstore'
date: 2014-10-27 02:34
comments: true
header-img: "assets/common/chrome-bg.jpg"
author:     "任平生"
tags:
    - Chrome
---

<img src="/assets/2014/10/open-itunes.jpg" alt="open-itunes.jpg" width="400">


在 Chrome 里点 iTunes/Mac Appstore 里的打开链接，不能正确启动 iTunes/Mac AppStore，重新启用的方法是：


打开目录：

``` 
Mac OS X
~/Library/Application Support/Google/Chrome/
```

``` 
Windows7
%LocalAppData%/Google/Chrome/User Data/

```

找到  `Local State` 文件，在其中搜索：`itmss` 、`macappstores` ，将其值修改为 `false`

```
"itmss": false,
"macappstores": false,
```

此方法同样适用于 Chrome 自动启动 iTunes/Mac AppStore ，修改为 false 后，就可以阻止其自动启动 iTunes/Mac AppStore。