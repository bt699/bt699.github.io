---
layout: post
title:  "scrapy loader processors Identity!"
date:   2019-01-12 13:19:48 +0800
categories: processors

---
# from scrapy.loader.processors import Identity#
内置的处理器Identity，它表示最简单的处理器，什么都不做。它返回原始值不变。它不接收任何构造函数参数，也不接受Loader上下文。

# 实例1 #

{% highlight ruby %}
Python 3.7.0 (v3.7.0:1bf9cc5093, Jun 27 2018, 04:59:51) [MSC v.1914 64 bit (AMD64)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> from scrapy.loader.processors import Identity
>>> proc = Identity()
>>> proc(['one','two','three'])
['one', 'two', 'three']
{% endhighlight %}



内置的处理器Identity，它表示最简单的处理器，对数据不做任何处理的处理器。最简单的一个 processor，并不做任何事情，它的功能只是将原有的值照原样输出。

