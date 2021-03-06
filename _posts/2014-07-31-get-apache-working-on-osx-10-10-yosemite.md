---
layout: post
title: "解决升级 Yosemite 后， Web Server 不工作的问题"
description: "升级 10.10 的 Yosemite 后， 系统自带的 Apache Server 就出问题了， ~username/ 死活访问不到，找到问题"
keyword: "Yosemite, OSX, MAC, Web Server"
date: 2014-07-31 03:35
comments: true
author:     "任平生"
header-img: "assets/common/server-bg.jpg"
thumb-img: "assets/common/server-thumb.jpg"
tags:
    - Apache
    - OSX
    - Yosemite
---
升级 10.10 的 Yosemite 后， 系统自带的 [Apache Server](http://note.rpsh.net/posts/2013/11/27/osx-10-9-apache-server-php-mysql) 就出问题了， `~username/` 死活访问不到，找到问题[解决方案](http://coolestguidesontheplanet.com/get-apache-mysql-php-phpmyadmin-working-osx-10-10-yosemite/)如下：

编辑 `username.config` 文件：
```
sudo vi /etc/apache2/users/username.config
```
添加 `Require all granted`

```conf
<Directory "/Users/username/Sites/">
Options Indexes MultiViews FollowSymLinks
AllowOverride All
Order allow,deny
Allow from all
Require all granted
</Directory>
```

编辑 `/etc/apache2/httpd.conf` 文件，删除下列这些代码前的注释符号： `#`

```conf
Include /private/etc/apache2/extra/httpd-userdir.conf
```


```conf
LoadModule authz_core_module libexec/apache2/mod_authz_core.so
LoadModule authz_host_module libexec/apache2/mod_authz_host.so
LoadModule userdir_module libexec/apache2/mod_userdir.so
```

编辑 `/etc/apache2/extra/httpd-userdir.conf` 文件，删除下列这些代码前的注释符号： `#`

```conf
Include /private/etc/apache2/users/*.conf
```

最后，重启 Apache
```
sudo apachectl restart
```