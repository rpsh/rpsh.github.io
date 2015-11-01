---
layout: post
title: 'Mac OS X 安装 PHP intl 扩展'
date: 2015-10-07 10:26
comments: true
header-img: "assets/common/php-bg.jpg"
author:     "任平生"
tags:
    - OSX
    - PHP
    - Apache
---
首先，需要关掉 MAC OS X El Captian 的 System Integrity Protection（rootless）的[机制](https://www.quora.com/How-do-I-turn-off-the-rootless-in-OS-X-El-Capitan-10-11)：

    1. 重启计算机时按住 Command 和 R 键进入到恢复模式
    2. 恢复模式启动后，从顶部菜单栏中选择 “实用工具 > 终端”
    3. 在终端窗口中输入csrutil disable并按回车键
    4. 重启系统，System Integrity Protection 就会被关闭了

启用 PEAR

```
cd /usr/lib/php
sudo php install-pear-nozlib.phar
sudo pear channel-update pear.php.net
sudo pecl channel-update pecl.php.net
sudo pear upgrade-all
```

使用 Homebrew 安装 ICU 库

```
brew install icu4c
```

安装 intl 

```
sudo pecl install intl
```

icu4c path: `/usr/local/opt/icu4c/`

编辑 `/etc/php.ini` 在最后添加：

```
extension=intl.so
```

重启 Apache

```
sudo apachectl restart
```

检查是否安装成功

```sh
php -m | grep intl #正常会返回 'intl'
```

----

## 手动安装步骤

手动安装 ICU（[ICU下载](http://download.icu-project.org/files/icu4c/52.1/icu4c-52_1-src.tgz)）

```
tar xzvf icu4c-52_1-src.tgz
cd icu/source
./runConfigureICU MacOSX
make
sudo make install
```

手动安装 intl （ [PHP源](http://www.php.net/get/php-5.5.29.tar.gz/from/a/mirror) ）

```
cd ext/intl
phpize
./configure --enable-intl
make
sudo cp modules/intl.so /usr/lib/php/extensions/no-debug-non-zts-??????/
```

参考资料

* [Installing the PHP intl extension on OS X Mavericks](http://codingexplained.com/operating-systems/mac/installing-php-intl-extension-os-x-mavericks)
* [Setting up PHP & MySQL on OS X Yosemite](http://akrabat.com/setting-up-php-mysql-on-os-x-yosemite/)
* [PHP WITH INTL AND GETTEXT ON OSX LION](http://mansion.im/2011/php-with-intl-and-gettext-on-osx-lion/)
