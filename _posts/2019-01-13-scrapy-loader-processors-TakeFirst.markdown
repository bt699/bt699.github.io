---
layout: post
title:  "scrapy loader processors TakeFirst!"
date:   2019-01-13 13:19:48 +0800
categories: processors

---
# from scrapy.loader.processors import TakeFirst#
内置的处理器TakeFirst，它表示从接收到的值中返回第一个非空（non-null/non-empty）值，因此通常用作单值字段的输出处理器。它不接收任何构造参数，也不接收Loader上下文。

# 实例1 #

{% highlight ruby %}
Python 3.7.0 (v3.7.0:1bf9cc5093, Jun 27 2018, 04:59:51) [MSC v.1914 64 bit (AMD64)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> from scrapy.loader.processors import TakeFirst
>>> proc1=TakeFirst()
>>> proc1(['one','two','three'])
'one'
{% endhighlight %}
# 实例2 #
E:\gitwenjian\scra\itlo\itlo\items.py文件内容
{% highlight ruby %}
# -*- coding: utf-8 -*-

# Define here the models for your scraped items
#
# See documentation in:
# https://doc.scrapy.org/en/latest/topics/items.html

import scrapy
from scrapy.loader import ItemLoader
from scrapy.loader.processors import TakeFirst,MapCompose,Join
from w3lib.html import remove_tags

def filter_price(value):
    if value.isdigit():
        return value

class ItloItem(scrapy.Item):
    # define the fields for your item here like:
    # name = scrapy.Field()
    pass

class Product(scrapy.Item):
    name = scrapy.Field(
        input_processor=MapCompose(remove_tags),
        output_processor=Join(),
    )
    price = scrapy.Field(
        input_processor=MapCompose(remove_tags,filter_price),
        output_processor=TakeFirst(),
    )
    stock = scrapy.Field()
    last_updated = scrapy.Field(serializer=str)

class ProductLoader(ItemLoader):
    default_input_processor = TakeFirst()
    name_in = MapCompose(str.title)
    name_out = Join()

    price_in = MapCompose(str.strip)


{% endhighlight %}

{% highlight ruby %}
E:\gitwenjian\scra\itlo\itlo>il = ItemLoader(item=Product())
'il' 不是内部或外部命令，也不是可运行的程序
或批处理文件。

E:\gitwenjian\scra\itlo\itlo>python
Python 3.7.0 (v3.7.0:1bf9cc5093, Jun 27 2018, 04:59:51) [MSC v.1914 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> from scrapy.loader import ItemLoader
>>>
>>> from items import Product
>>> il = ItemLoader(item=Product())
>>> il.add_value('name', [u'Welcome to my', u'<strong>website</strong>'])
>>>
>>>
>>> il.add_value('price', [u'&euro;', u'<span>1000</span>'])
>>> il.load_item()
{'name': 'Welcome to my website', 'price': '1000'}
>>>
{% endhighlight %}


内置的处理器TakeFirst，它的功能只是将原有多个值数据只输出一个值(空值除外)。

