---
layout: post
title:  "python split 方法!"
date:   2019-01-08 13:19:48 +0800
categories: python

---
# python split() 方法  #
Python split() 通过指定分隔符对字符串进行切片，默认为所有的空字符，包括空格、换行(\n)、制表符(\t)等。

# 实例1 #

{% highlight ruby %}
>>> x = '5.7'
>>> x.split('.')
['5', '7']
>>> x.split('.')[0]
'5'

{% endhighlight %}

以上代码指定分隔符'点'对字符串进行切片

# 实例2 #


{% highlight ruby %}
>>> z = '    5.7   '
>>> z1 = x.split('.')[0]
>>> z1 = z.split('.')[0]
>>> z1
'    5'
>>> z1.strip()
{% endhighlight %}


以上代码指定分隔符'点'对字符串进行切片，用[strip][strip]方法去掉前后空格。

# 输出 #
{% highlight ruby %}
'5'
{% endhighlight %}

[strip]:https://bt699.github.io/python/2019/01/07/python-strip.html