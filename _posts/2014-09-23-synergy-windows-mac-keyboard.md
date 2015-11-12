---
layout: post
title: 'synergy: 一套键鼠控制多台 Mac 与 Windows'
description: "Synergy 可以用来连接多台 Mac 与 Windows，操控它们只需要一套键鼠"
keyword: "Synergy"
date: 2014-09-23 06:17
comments: true
author:     "任平生"
tags:
    - Soft
    - synergy
---
安装 [Synergy](http://synergy-project.org/) 后，就可以用一套键鼠控制局域网里的多台电脑，支持 Windows、Mac、Linux 多系统。

![synergy-1.png](/assets/2014/09/synergy-1.png)



我是使用 Mac 作为服务端，使用 Mac 的键鼠去控制 Windows，由于习惯了 Mac 键盘的 Command 作为类似 Ctrl 的组合键，于是设置 Command 映射 Windows 的 Ctrl 键，control 映射 Win 键，映射方法：

    1. 打开 Configure Server
    2. 双击 PC 的图标
    3. 设置 ctrl -> Super; Super-> Ctrl
    4. 依次点击 Ok, Apply

![synergy-2.png](/assets/2014/09/synergy-2.png)

