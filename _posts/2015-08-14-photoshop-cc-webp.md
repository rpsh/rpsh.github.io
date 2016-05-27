---
layout: post
title: "Adobe Photoshop CC 导出 Webp 格式图片"
description: "通过安装 WebP 插件，让 Adobe Photoshop CC 支持导出 WebP 格式图片"
keyword: "WebP, Photoshop, WebPFormat, WebPQuickLook "
date: 2015-08-14 12:00
comments: true
author:     "任平生"
header-img: "assets/common/photoshop-bg.jpg"
thumb-img: "assets/common/photoshop-thumb.jpg"
tags:
    - Photoshop
    - WebP
---

首先，下载插件： [WebP Format](http://telegraphics.com.au/sw/product/WebPFormat)

Windows 将 `WebPFormat64.8bi` 丢进：
```
C:\Program Files\Adobe\Adobe Photoshop CC 2015\Plug-ins
```

Mac OS X 将 `WebPFormat.plugin` 文件丢进：
```
/Applications/Adobe Photoshop CC 2015/Plug-ins
```

重启你的 Adobe Photoshop ，在「另存为」菜单中就可以找到 WebP 格式了。
![WebPQuickLook](http://note.rpsh.net/assets/2015/08/webp-photoshop-plugin.jpg)


Mac OS X 上如果想用 QuickLook 预览 WebP 格式文件，可以安装这个插件： [WebPQuickLook](https://github.com/emin/WebPQuickLook)

其他一些小工具：
[WebPonize](https://webponize.github.io/) Mac 上一款将图片转为 WebP 的小工具，[下载](https://github.com/1000ch/WebPonize/raw/master/webponize.tar.gz)
[cwebp 命令行](https://developers.google.com/speed/webp/docs/cwebp) `cwebp -q 80 example.png -o example.webp`
[WebP 在线转换 1](http://image.online-convert.com/convert-to-webp), [2](https://webp-converter.com/)
[让 Windows 支持预览 WebP 图片](https://developers.google.com/speed/webp/docs/webp_codec)


参考链接：
	- [Complete Guide to Using WebP Image Format](http://www.hongkiat.com/blog/webp-guide/)
