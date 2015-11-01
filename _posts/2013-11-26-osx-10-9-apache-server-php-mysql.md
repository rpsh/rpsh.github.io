---
layout: post
title: 'Mac OS X 启用 Web 服务器'
date: 2013-11-26 16:22
comments: true
author:     "任平生"
header-img: "assets/common/apache-bg.jpg"
tags:
    - OSX
    - Apache
    - PHP
    - Mysql
---

原文： [Get Apache, MySQL, PHP and phpMyAdmin working on OSX 10.9 Mavericks](http://www.coolestguidesontheplanet.com/downtown/get-apache-mysql-php-and-phpmyadmin-working-osx-109-mavericks)

*Update: 2014/10/28 修改文章添加在 Yosemite 上开启 Web Server 的[步骤](http://note.rpsh.net/posts/2014/07/31/get-apache-working-on-osx-10-10-yosemite/)*

Mac OS X 10.9 依旧预装了 Apache ，但是已经不能在 「系统偏好设置」中的「Web 共享」来开启了，需要手动通过命令行开启。

## 启动Apache

启动：`sudo apachectl start`

停止：`sudo apachectl stop`

重启：`sudo apachectl restart`

查看 Apache 版本 `httpd -v`

浏览器打开 http://127.0.0.1 可以看到 **It works!** 的页面

![Apache Works](/assets/2013/11/itworks.png)


### 文件根目录

#### 系统级的根目录 

`http://localhosts/`

对应的文件目录是：

`/Library/WebServer/Documents/`



系统级根目录默认没有开启目录列表，开启方法：

编辑 `/etc/apache2/httpd.conf` 文件

搜索找到 `<Directory "/Library/WebServer/Documents">`

将 `Options FollowSymLinks Multiviews` 修改为 

`Options Indexes FollowSymLinks Multiviews`

目录列表显示全部的文件名：

```
IndexOptions FancyIndexing NameWidth=* DescriptionWidth=* VersionSort FoldersFirst
IndexOptions Charset=UTF-8
```

#### 用户级根目录

另一个 Web 根目录默认是 `~/Sites` ，10.9 中你需要手动创建这个`Sites`目录。

![image](/assets/2013/11/sites-user-folder-osx-mavericks.png)

检查这个目录下是否有 `username.conf` 文件

`/etc/apache2/users/`

如果没有，则需要新建一个，`username` 需要是你的账户名字，建议使用终端创建这个文件：

`cd /etc/apache2/users`

`sudo vi username.conf`

贴入以下内容，注意修改 `username` 为你的账户名字

```
<Directory "/Users/username/Sites/">
Options Indexes MultiViews FollowSymLinks
AllowOverride All
Order allow,deny
Allow from all
Require all granted
</Directory>
```

这个文件的权限应该是：

`-rw-r--r--   1 root  wheel  298 Jun 28 16:47 username.conf`

如果不是，请修改

`sudo chmod 644 username.conf`

编辑 `/etc/apache2/httpd.conf` 文件，删除下列这些代码前的注释符号： `#`
```
Include /private/etc/apache2/extra/httpd-userdir.conf
```
```
LoadModule authz_core_module libexec/apache2/mod_authz_core.so
LoadModule authz_host_module libexec/apache2/mod_authz_host.so
LoadModule userdir_module libexec/apache2/mod_userdir.so
```

编辑 `/etc/apache2/extra/httpd-userdir.conf` 文件，删除下列这些代码前的注释符号： `#`
```
Include /private/etc/apache2/users/*.conf
```

重启 Apache

`sudo apachectl restart`

这时，这个网址应该已经可以用了：

`http://localhost/~username/`


 
#### 启用重定向 .htaccess

`sudo vi /etc/apache2/httpd.conf`

删除 AllowOverride all 前的注释 #



### PHP

OSX 10.9 已经预装了 PHP 5.4.17， 编辑 `httpd.conf`

`sudo vi /etc/apache2/httpd.conf`

取消这一行前边的注释符号 `#`

`LoadModule php5_module libexec/apache2/libphp5.so`

重启 Apache

`sudo apachectl restart`

查看 Apache 信息

`<?php phpinfo(); ?>`

php.ini 文件位置：
`/private/etc/php.ini.default` 可复制一份命名为： `/private/etc/php.ini`
(在终端里输入 `php --ini` 即可查的 php.ini 文件位置)

显示 PHP 错误
`display_errors = On`

## MySQL

OS X 10.9 需要单独安装 MySQL，[下载地址](http://dev.mysql.com/downloads/mysql/) ，选择 _Mac OS X ver. 10.7 (x86, 64-bit), DMG Archive_ 。（下载无需注册，点击下边小字部分的「_ No thanks, just take me to the downloads!_」即可）

![MySQL 安装](/assets/2013/11/mysql-install-osx-mavericks.png)

三个文件都需要安装。其中第二个会在「系统偏好设置」中添加一个 MySQL 设置项：开机自动启动、启动／关闭 MySQL

命令行启动 MySQL

`sudo /usr/local/mysql/support-files/mysql.server start `

查看 MySQL 版本

`/usr/local/mysql/bin/mysql -v`

添加 mysql 别名到 PATH 里：

`cd ; vi .bash_profile` 

添加：

`export PATH="/usr/local/mysql/bin:$PATH"`

保存退出，然后执行

`source ~/.bash_profile`

之后就可以直接使用 mysql 命令
`mysql -v`

使用 `\q` 可以退出 mysql 模式

### 设置 MySQL 密码

修改 mysql root 账户密码：

`/usr/local/mysql/bin/mysqladmin -u root password 'yourpasswordhere'`

**注意使用单引号包裹密码**

### 修复 2002 MySQL Socket 错误

`sudo mkdir /var/mysql`

`sudo ln -s /tmp/mysql.sock /var/mysql/mysql.sock`


## phpMyAdmin

安装前必须先如上操作修复 2002 MySQL Socket 错误。

[下载 phpMyAdmin](http://www.phpmyadmin.net/home_page/downloads.php) ，解压后放在 `~/Sites` 目录下，新建 `config` 文件夹

`mkdir ~/Sites/phpmyadmin/config`

修改权限

`chmod o+w ~/Sites/phpmyadmin/config`

打开 <http://127.0.0.1/~username/phpmyadmin/>
输入 mysql 的用户名和密码就可以登陆进去了。

然后删除 `/config` 目录。

phpMyAdmin 可能会提示：配置文件现在需要一个短语密码。
此时修改文件：
`phpMyAdmin/libraries/config.default.php`
找到：
`$cfg['blowfish_secret'] = '';`
修改为：
`$cfg['blowfish_secret'] = 'rpsh.net';` (rpsh.net 可以为任意字符)


访问 <http://127.0.0.1/~username/phpmyadmin/> 就可以管理你的 mysql 了。

## 权限

为了方便程序在 `~/Sites` 目录下读写

`sudo chmod -R a+w ~/Sites/testsite`

若担心安全问题，可以使用 _www 权限，若这样做当需要 admin 权限需做验证：

`sudo chown -R _www ~/Sites/testsite`
