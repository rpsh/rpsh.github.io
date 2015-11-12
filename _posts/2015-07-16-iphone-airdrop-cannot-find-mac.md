---
layout: post
title: "解决 iPhone AirDrop 找不到 Mac"
description: "升级到 El Caption 测试版后，iPhone 就死活不能 Airdrop 找到我的 Macbook 了，两个设备间互传文件变得异常麻烦，猜测应该是蓝牙的配置文件出问题了，试试删掉旧的配置文件后，果然问题就修复了"
keyword: "El Caption, AirDrop"
date: 2015-07-16 13:25
comments: true
header-img: "assets/common/iphone-bg.jpg"
thumb-img: "assets/common/iphone-thumb.jpg"
author:     "任平生"
tags:
    - iPhone
    - AirDrop
---
升级到 El Caption 测试版后，iPhone 就死活不能 Airdrop 找到我的 Macbook 了，两个设备间互传文件变得异常麻烦，猜测应该是蓝牙的配置文件出问题了，试试删掉旧的配置文件后，果然问题就修复了。

1. 在 Mac 上打开目录： `/Library/Preferences`
2. 找到文件： `com.apple.Bluetooth.plist` 删除之
3. 关掉蓝牙，重新打开蓝牙
4. 这时候 iPhone 的 Airdrop 就可以找到 Mac 了