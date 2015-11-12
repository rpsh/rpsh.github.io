---
layout: post
title: "修改 Chrome 搜索默认使用 Google.com"
description: "修改 Chrome 搜索默认使用 Google.com,首先关闭所有 Chrome 窗口，然后按一下操作"
keyword: "chrome, google.com"
date: 2013-04-29 12:01
comments: true
author:     "任平生"
header-img: "assets/common/chrome-bg.jpg"
thumb-img: "assets/common/chrome-thumb.jpg"
tags:
    - Chrome
    - Google
---


修改 Chrome 搜索默认使用 Google.com  
  
首先关闭所有 Chrome 窗口，然后按一下操作：  
  

1. 
	*  Windows:   
	转到目录 `%LOCALAPPDATA%\Google\Chrome\User Data\Default\Preferences`
	* Mac:  
	转到目录 `~/Library/Application Support/Google/Chrome` 

2. 打开 Local State 文件
3. 添加：

	```json
	"last_known_google_url": "http://www.google.com/",  
	"last_prompted_google_url": "http://www.google.com/",
	```



