---
layout: post
title: "使用 ffmpeg 实现 MP4 与 GIF 的互转"
description: "使用 ffmpeg 将 mp4 转为 gif，可以设置缩小尺寸，提取某一帧图片，设置转换为 gif 的图片质量。"
keyword: "ffmpeg, gif, mp4, mp4转gif, gif转mp4"
date: 2015-04-21 14:00
comments: true
author:     "任平生"
tags:
    - ffmpeg
    - gif
    - mp4
---

在 Mac OSX 上使用 [Homebrew](http://brew.sh/) 安装 [ffmpeg](https://www.ffmpeg.org/)：

``` bash
brew install ffmpeg

brew install ffmpeg --with-fdk-aac --with-ffplay --with-freetype --with-libass --with-libquvi --with-libvorbis --with-libvpx --with-opus --with-x265

brew update && brew upgrade ffmpeg
```

## 将视频 MP4 转化为 GIF

``` 
ffmpeg -i small.mp4 small.gif
```

### 转化视频中的一部分为 GIF

``` 
ffmpeg -t 3 -ss 00:00:02 -i small.webm small-clip.gif
```

从视频中第二秒开始，截取时长为3秒的片段转化为 gif

### 转化高质量 GIF

默认转化是中等质量模式，若要转化出高质量的 gif，可以修改比特率

``` 
ffmpeg -i small.mp4 -b 2048k small.gif
```



## 视频属性调整

### 缩放视频尺寸

``` 
ffmpeg -i big.mov -vf scale=360:-1  small.mov
```

注意 `sacle` 值必须是偶数，这里的 `-1` 表示保持长宽比，根据宽度值自适应高度。

### 加倍速播放视频

``` 
ffmpeg -i input.mov -filter:v "setpts=0.5*PTS" output.mov
```

定义帧率 16fps:

``` 
ffmpeg -i input.mov -r 16 -filter:v "setpts=0.125*PTS" -an output.mov
```

### 慢倍速播放视频

``` 
ffmpeg -i input.mov -filter:v "setpts=2.0*PTS" output.mov
```

### 静音视频（移除视频中的音频）

``` 
ffmpeg -i input.mov -an mute-output.mov
```

`-an` 就是禁止音频输出 

## 将 GIF 转化为 MP4

``` 
ffmpeg -f gif -i animation.gif animation.mp4
```

也可以将 gif 转为其他视频格式

``` 
ffmpeg -f gif -i animation.gif animation.mpeg

ffmpeg -f gif -i animation.gif animation.webm
```

## 获取 GIF 的第一帧图片

使用 [ImageMagick](http://www.imagemagick.org/) 可以方便第提取 gif 图片的第 N 帧图像。

安装 ImageMagick

``` 
brew install imagemagick
```

提取第一帧

``` 
convert 'animation.gif[0]' animation-first-frame.gif
```

通过 `[0]` 就可以提取出 gif 的第一帧图像。



参考资料

* [FFmpeg CompilationGuide/MacOSX](https://trac.ffmpeg.org/wiki/CompilationGuide/MacOSX)
* [Convert Video to GIF or GIF to Video](http://davidwalsh.name/convert-video-gif)
* [Get the First Frame of an Animated GIF with ImageMagick](http://davidwalsh.name/first-frame-animated-gif)
* [Create an Image Preview from a Video](http://davidwalsh.name/create-image-preview-video)
* [How to speed up / slow down a video](https://trac.ffmpeg.org/wiki/How%20to%20speed%20up%20/%20slow%20down%20a%20video)
* [ffmpeg useful commands (FFMPEG 命令大全）](http://siwei.me/blog/posts/ffmpeg-useful-commands) 
* [ffmpeg 文档](http://siwei.me/blog/posts/ffmpeg-useful-commands) 