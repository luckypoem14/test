---
layout: post
title: blog改造
categories:
- 无
description: 原型,评论,代码高亮,css,优化
---
原型参考
http://yihui.name/cn
下载地址
https://github.com/yihui/cn
如今已完全变样
# 
- 导航放上面
- 评论用**多说**,加个按钮，切换到disqus
- **jiathis**
- 代码高亮用 **google-code-prettify**
# 
css主要变化  
我的23寸显示器，1920*1080分辨率
字体设大点
<pre class="prettyprint">
@media screen and (max-width:1600px){} 
	body{font-size:26px;}
}

</pre>

markdown忽略空格问题，想让一些文字段落首行缩进几个字符，用 pre-wrap,还不是很理想
<pre class="prettyprint">
p{padding:.3em 0;white-space:pre-wrap;}

</pre>

**圆角**  
标题 **text-shadow**

参考 **浩宇啸天** ,blog 首页换成分页式,加个Archives

_layouts\default.html

<pre class="prettyprint"><code>
<xmp><!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN" lang="zh-cn">
<head>
	<meta http-equiv="content-type" content="text/html; charset=utf-8" />
	<meta http-equiv="cache-control" content="max-age=7200" />
	<meta name="author" content="{{ site.author }}" />
	<title>{{ page.title }}</title>
	<link rel="shortcut icon" href="{{ site.url }}/favicon.ico">
	<link rel="openid.server" href="http://www.myopenid.com/server" />
	<link rel="openid.delegate" href="http://ddatsh.myopenid.com" />
	<link href="{{ site.url }}/feed/" rel="alternate" title="{{ site.author }}" type="application/atom+xml" />
	<!--[if lte IE 7]><style>* {display:none}</style><![endif]-->
	
	<!--<link rel="stylesheet" href="{{ site.url }}/media/css/style.css">-->
	<!--<link href="{{ site.url }}/media/google-code-prettify/prettify.css" type="text/css" rel="stylesheet" />-->
	<!--sunburst.css is google-code-prettify theme   -->
	<!--<link rel="stylesheet" href="{{ site.url }}/media/css/sunburst.css" />-->
	<!--compact style.css&prettify.css&sunburst.css-->
	<style></style>
	
	<!--<script src="{{ site.url }}/media/google-code-prettify/prettify.js"></script>-->
	<!--compact prettify.js-->
	<script></script>
	
	<!--<script src="{{ site.url }}/media/js/jquery-1.7.1.min.js"></script>-->
	<!--compact jquery-1.7.1.min.js-->
	<script></script>
	
	<!--use define script,such as disable select-->
	<script></script>
	
</head>

<body onload="prettyPrint()">
	<div id="container">
	      <div id="main">
			<header><h1>{{ page.title }}</h1></header>
			<div class="nav">
				<a title="home page" class="" href="{{ site.url }}/">Index</a>
				<a title="about" class="" href="{{ site.url }}/about/">About</a>
				<a title="categories" class="" href="{{ site.url }}/categories/">Tags</a>
				<a title="categories" class="" href="{{ site.url }}/archives/">Archives</a>
				<a title="subscribe by RSS" class="" href="{{ site.url }}/feed/">Feed</a>
			</div>
			<div class="content">
		 	<div class="post">
				{{ content }}
				</div>
			</div>
		</div>
	</div>
	<script>
		if( location.host != "localhost"){
		 	/*jQuery.getScript("http://www.google-analytics.com/ga.js",
		 		function(){
		 			try {
		 				var pageTracker = _gat._getTracker("UA-30498868-1");
		 				pageTracker._trackPageview();
		 			} catch(err) {}}
		 		);*/
		 	//jQuery.getScript("http://w.cnzz.com/c.php?id=30020727",function(){});
		 	jQuery.getScript("http://hm.baidu.com/h.js?4ccc600c017878e1d3486a2191649db4",
		 		function(){});
		}
	</script>
</body>
</html>
</xmp></code></pre>

将JS和CSS压缩
页面最下面,统计脚本,只用百度
