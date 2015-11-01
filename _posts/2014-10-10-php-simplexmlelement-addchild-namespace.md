---
layout: post
title: 'PHP SimpleXMLElement 添加带 Namespace 的节点'
date: 2014-10-10 14:46
comments: true
header-img: "assets/common/php-bg.jpg"
author:     "任平生"
tags:
    - PHP
    - XML
---

```xml
<?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0"
	xmlns:itunes="http://www.itunes.com/dtds/podcast-1.0.dtd"
>
	<channel>
		<title>IT 乱谈</title>
		<link>http://itluantan.com/</link>
		<item>
			<title>#01 第一次亲密接触</title>
			<itunes:author>IT 乱谈</itunes:author>
			<itunes:explicit>no</itunes:explicit>
		</item>
	</channel>
</rss>
```

使用 PHP SimpleXMLElement 生成 feed 的 xml 文件时候，怎么添加带 `namespace` 的节点：
查手册 [addAttribute](http://php.net/simplexmlelement.addattribute) ，语法是这样：

```php
addAttribute ( string $name [, string $value [, string $namespace ]] )
```

于是，代码这么写

```php
$xml_root = "<?xml version=\"1.0\" encoding=\"UTF-8\" ?><rss></rss>";
$xml = new SimpleXMLElement($xml_root);
$xml -> addAttribute('itunes', 'http://www.itunes.com/dtds/podcast-1.0.dtd', 'xmlns');
```

但总是报错：

```
Warning:  SimpleXMLElement::addAttribute(): Attribute requires prefix for namespace in 
```

搜索后修改写法：

```php
$xml_root = "<?xml version=\"1.0\" encoding=\"UTF-8\" ?>".
			"<rss version=\"2.0\" xmlns:itunes=\"http://www.itunes.com/dtds/podcast-1.0.dtd\"></rss>";
$xml = new SimpleXMLElement($xml_root);
```
这下 OK 了。

`<item>` 里添加带 `namespace` 的节点时：

```php
$xml_item -> addChild('itunes:author', 'IT乱谈', 'http://www.itunes.com/dtds/podcast-1.0.dtd');
```




搜索时，发现[另一种写法](http://stackoverflow.com/questions/6927567/adding-a-namespace-when-using-simplexmlelement)：

```php
$xml_item -> addChild('test:itunes:author', 'IT乱谈');
```

`test:itunes:author` 前缀的前缀（test可以是任意字符），可以偷懒不用每次都写 namespace uri 。
