---
layout: post
title: "OS X Yosemite 如何删掉 Launchpad 里下载不成功的图标"
description: "在 Yosemite 中遇到类似这样下载失败的图标，按住 option 也不能删除掉"
keyword: "Yosemite, ghost icon"
date: 2014-08-22 05:23
comments: true
author:     "任平生"
tags:
    - OSX
    - Yosemite
---
在 Yosemite 中遇到类似这样下载失败的图标，按住 option 也不能删除掉

![ghost-icon.png](http://note.rpsh.net/assets/2014/08/ghost-icon.png)


删除方法：

```
sudo rm -rf ~/Library/Application\ Support/Dock
```
输入密码，然后再执行

```
killall Dock
```

执行后我这里依然遗留了1个图标没有删除，重复上述步骤后，总算把所有的这些 ghost 图标删掉了。

PS：执行这个操作后 Launchpad 中的图标排列依然会保持你整理后的排版