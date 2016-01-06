---
layout: post
title: "HTML5 表单自动填表功能"
description: "使用 autocomplete 属性可以为表单提供自动填表能力"
keyword: "自动填表, autocomplete"
date: 2015-04-16 11:00
comments: true
author:     "任平生"
header-img: "assets/common/html5-bg.jpg"
thumb-img: "assets/common/html5-thumb.jpg"
tags:
    - HTML5
    - HTML/autocomplete
---
使用 `autocomplete` 属性可以为表单提供自动填表能力：

<img src="http://note.rpsh.net/assets/2015/04/autocomplete.png" alt="autocomplete.png" />



```html
<input type="text" name="name" autocomplete="name">

<input type="email" name="email" autocomplete="email">

<input type="tel" name="phone" autocomplete="tel">
```

HTML5 表单的自动填表已经成为 [WHATWG HTML 标准](https://html.spec.whatwg.org/multipage/forms.html#autofill)的一部分了，`autocomplete`  可以使用的取值有以下这些：


<table>
	<thead>
		<tr>
			<th colspan="4">autocomplete 取值</th>
			<th> 含义</th>
			<th> 取值格式</th>
			<th> 取值示例</th>
			<th> Control group</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td colspan="4"><code>name</code></td>
			<td>全名</td>
			<td>单行任意文字</td>
			<td>Sir Timothy John Berners-Lee,<br>OM, KBE, FRS, FREng, FRSA</td>
			<td>Text</td>
		</tr>
		<tr>
			<td class="" rowspan="5"></td>
			<td colspan="3"><code>honorific-prefix</code></td>
			<td>名字前的尊称 (e.g. "Mr.", "Ms.", "Dr.", "<span lang="fr">M<sup>lle</sup></span>")</td>
			<td>单行任意文字</td>
			<td>Sir</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>given-name</code></td>
			<td>名字</td>
			<td>单行任意文字</td>
			<td>Timothy</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>additional-name</code></td>
			<td>中间名</td>
			<td>单行任意文字</td>
			<td>John</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>family-name</code></td>
			<td>姓氏</td>
			<td>单行任意文字</td>
			<td>Berners-Lee</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>honorific-suffix</code></td>
			<td>名字后的尊称，一般都是封衔 (e.g. "Jr.", "B.Sc.", "MBASW", "II")</td>
			<td>单行任意文字</td>
			<td>OM, KBE, FRS, FREng, FRSA</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>nickname</code></td>
			<td>昵称</td>
			<td>单行任意文字</td>
			<td>Tim</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>organization-title</code></td>
			<td>职称 (e.g. "Software Engineer", "Senior Vice President", "Deputy Managing Director")</td>
			<td>单行任意文字</td>
			<td>Professor</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>username</code></td>
			<td>用户名</td>
			<td>单行任意文字</td>
			<td>timbl</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>new-password</code></td>
			<td>新密码 (e.g. 新建账户或者修改密码时)</td>
			<td>单行任意文字</td>
			<td>GUMFXbadyrS3</td>
			<td>Password</td>
		</tr>
		<tr>
			<td colspan="4"><code>current-password</code></td>
			<td>当前 <code>username</code> 对应的密码 (e.g. 登陆时)</td>
			<td>单行任意文字</td>
			<td>qwerty</td>
			<td>Password</td>
		</tr>
	</tbody>
	<tbody>
		<tr>
			<td colspan="4"><code>organization</code></td>
			<td>公司、组织名</td>
			<td>单行任意文字</td>
			<td>World Wide Web Consortium</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>street-address</code></td>
			<td>街道地址 (多行)</td>
			<td>Free-form text</td>
			<td>32 Vassar Street
				<br> MIT Room 32-G524</td>
			<td>多行文字</td>
		</tr>
		<tr>
			<td class="non-rectangular-cell-indentation" rowspan="3"></td>
			<td colspan="3"><code>address-line1</code></td>
			<td rowspan="3">街道地址 (单行)</td>
			<td>单行任意文字</td>
			<td>32 Vassar Street</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>address-line2</code></td>
			<td>单行任意文字</td>
			<td>MIT Room 32-G524</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>address-line3</code></td>
			<td>单行任意文字</td>
			<td></td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>address-level4</code></td>
			<td>乡、镇</td>
			<td>单行任意文字</td>
			<td></td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>address-level3</code></td>
			<td>区、县</td>
			<td>单行任意文字</td>
			<td></td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>address-level2</code></td>
			<td>城市</td>
			<td>单行任意文字</td>
			<td>Cambridge</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>address-level1</code></td>
			<td>州、省、直辖市</td>
			<td>单行任意文字</td>
			<td>MA</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>country</code></td>
			<td>国家代码</td>
			<td>Valid <a href="http://www.iso.org/iso/country_codes/iso_3166_code_lists/country_names_and_code_elements.htm">ISO 3166-1-alpha-2 country code</a> <a href="https://html.spec.whatwg.org/multipage/references.html#refsISO3166">[ISO3166]</a></td>
			<td>US, CN</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>country-name</code></td>
			<td>国家名字</td>
			<td>单行任意文字; <a href="https://html.spec.whatwg.org/multipage/forms.html#autofill-country">有时来自 <code>country</code></a></td>
			<td>US</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>postal-code</code></td>
			<td>邮政编码</td>
			<td>单行任意文字</td>
			<td>02139</td>
			<td>Text</td>
		</tr>
	</tbody>
	<tbody>
		<tr>
			<td colspan="4"><code>cc-name</code></td>
			<td>信用卡持卡人全名</td>
			<td>单行任意文字</td>
			<td>Tim Berners-Lee</td>
			<td>Text</td>
		</tr>
		<tr>
			<td class="non-rectangular-cell-indentation" rowspan="3"></td>
			<td colspan="3"><code>cc-given-name</code></td>
			<td>信用卡持卡人名字</td>
			<td>单行任意文字</td>
			<td>Tim</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>cc-additional-name</code></td>
			<td>信用卡持卡人中间名</td>
			<td>单行任意文字</td>
			<td></td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>cc-family-name</code></td>
			<td>信用卡持卡人姓氏</td>
			<td>单行任意文字</td>
			<td>Berners-Lee</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>cc-number</code></td>
			<td>信用卡卡号</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a></td>
			<td>4114360123456785</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>cc-exp</code></td>
			<td>信用卡过期时间</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-month-string">Valid month string</a></td>
			<td>2014-12</td>
			<td>Month</td>
		</tr>
		<tr>
			<td class="non-rectangular-cell-indentation" rowspan="2"></td>
			<td colspan="3"><code>cc-exp-month</code></td>
			<td>信用卡过期时间－月份</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-date-string">Valid integer</a> in the range 1..12</td>
			<td>12</td>
			<td>Numeric</td>
		</tr>
		<tr>
			<td colspan="3"><code>cc-exp-year</code></td>
			<td>信用卡过期时间－年份</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-date-string">Valid integer</a> greater than zero</td>
			<td>2014</td>
			<td>Numeric</td>
		</tr>
		<tr>
			<td colspan="4"><code>cc-csc</code></td>
			<td>信用卡三位安全码</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a></td>
			<td>419</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>cc-type</code></td>
			<td>信用卡发卡组织</td>
			<td>单行任意文字</td>
			<td>Visa</td>
			<td>Text</td>
		</tr>
	</tbody>
	<tbody>
		<tr>
			<td colspan="4"><code>transaction-currency</code></td>
			<td>交易货币</td>
			<td>ISO 4217 currency code <a href="references.html#refsISO4217">[ISO4217]</a></td>
			<td>GBP</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>transaction-amount</code></td>
			<td>交易总额 (e.g. 出价或投标时使用)</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-floating-point-number">Valid floating-point number</a></td>
			<td>401.00</td>
			<td>Numeric</td>
		</tr>
	</tbody>
	<tbody>
		<tr>
			<td colspan="4"><code>language</code></td>
			<td>首选语言</td>
			<td>Valid BCP 47 language tag <a href="references.html#refsBCP47">[BCP47]</a></td>
			<td>en</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>bday</code></td>
			<td>出生日期年月日</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-date-string">Valid date string</a></td>
			<td>1955-06-08</td>
			<td>Date</td>
		</tr>
		<tr>
			<td class="non-rectangular-cell-indentation" rowspan="3"></td>
			<td colspan="3"><code>bday-day</code></td>
			<td>出生日期－日期</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-date-string">Valid integer</a> in the range 1..31</td>
			<td>8</td>
			<td>Numeric</td>
		</tr>
		<tr>
			<td colspan="3"><code>bday-month</code></td>
			<td>出生日期－月份</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-date-string">Valid integer</a> in the range 1..12</td>
			<td>6</td>
			<td>Numeric</td>
		</tr>
		<tr>
			<td colspan="3"><code>bday-year</code></td>
			<td>出生日期－年份</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-date-string">Valid integer</a> greater than zero</td>
			<td>1955</td>
			<td>Numeric</td>
		</tr>
		<tr>
			<td colspan="4"><code>sex</code></td>
			<td>性别 (e.g. 男, 女)</td>
			<td>单行任意文字</td>
			<td>Male</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>url</code></td>
			<td>网址</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-url">Valid URL</a></td>
			<td style="padding: 0;">http://www.w3.org/</td>
			<td>URL</td>
		</tr>
		<tr>
			<td colspan="4"><code>photo</code></td>
			<td>照片、图标、或其他图片</td>
			<td> <a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-url">Valid URL</a></td>
			<td style="padding: 0;">http://www.w3.org/2015/03/w3cx-logo.png</td>
			<td> URL</td>
		</tr>
	</tbody>
	<tbody>
		<tr>
			<td colspan="4"><code>tel</code></td>
			<td>电话号码，包含国家码</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a> and U+0020 SPACE characters, prefixed by a U+002B PLUS SIGN character (+)</td>
			<td>+1 617 253 5702</td>
			<td>Tel</td>
		</tr>
		<tr>
			<td class="non-rectangular-cell-indentation" rowspan="6"></td>
			<td colspan="3"><code>tel-country-code</code></td>
			<td>国际区号</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a> prefixed by a U+002B PLUS SIGN character (+)</td>
			<td>+1</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="3"><code>tel-national</code></td>
			<td>不包含国际区号的电话号码</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a> and U+0020 SPACE characters</td>
			<td>617 253 5702</td>
			<td>Text</td>
		</tr>
		<tr>
			<td class="non-rectangular-cell-indentation" rowspan="4"></td>
			<td colspan="2"><code>tel-area-code</code></td>
			<td>区号</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a></td>
			<td>617</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="2"><code>tel-local</code></td>
			<td>不包含国际区号、区号的电话号码</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a></td>
			<td>2535702</td>
			<td>Text</td>
		</tr>
		<tr>
			<td class="non-rectangular-cell-indentation" rowspan="2"></td>
			<td><code>tel-local-prefix</code></td>
			<td>本地电话号码前缀</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a></td>
			<td>253</td>
			<td>Text</td>
		</tr>
		<tr>
			<td><code>tel-local-suffix</code></td>
			<td>本地电话号码后缀</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a></td>
			<td>5702</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>tel-extension</code></td>
			<td>分机</td>
			<td><a id="" href="https://html.spec.whatwg.org/multipage/infrastructure.html#ascii-digits">ASCII digits</a></td>
			<td>1000</td>
			<td>Text</td>
		</tr>
		<tr>
			<td colspan="4"><code>email</code></td>
			<td>E-mail 地址</td>
			<td>Valid e-mail address</td>
			<td>timbl@w3.org</td>
			<td>E-mail</td>
		</tr>
		<tr>
			<td colspan="4"><code>impp</code></td>
			<td>IM软件的伪协议链接 (e.g. "<code>aim:goim?screenname=NAME</code>" or "<code>xmpp:fred@example.net</code>")</td>
			<td><a href="https://html.spec.whatwg.org/multipage/infrastructure.html#valid-url">Valid URL</a></td>
			<td>irc://example.org/timbl,isuser</td>
			<td>URL</td>
		</tr>
	</tbody>
</table>


示例：
<iframe width="100%" height="300" src="https://googlesamples.github.io/web-fundamentals/samples/input/form/order.html"></iframe>

若要禁用自动填表，`autocomplete` 取值 `off`。

```html
<input type="text" name="pin" autocomplete="off">
```

参考资料：

[Label and name inputs properly](https://developers.google.com/web/fundamentals/input/form/label-and-name-inputs)


<style>
td[colspan="3"]{
	white-space: nowrap;
	border-left: 1px solid #dedede;
}
td{
	border-right: 1px solid #dedede;
}
tbody{
	border-bottom: 1px solid #dedede;
}
td code{
	white-space: nowrap;
}
</style>