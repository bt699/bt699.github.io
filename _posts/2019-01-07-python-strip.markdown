---
layout: post
title:  "python strip 方法!"
date:   2019-01-07 13:19:48 +0800
categories: python

---
# python strip() 方法  #
Python strip() 该方法只能删除开头或是结尾的字符，不能删除中间部分的字符。

# 实例1 #

{% highlight ruby %}
>>> y = '---Plasma TV---'
>>> y.strip()
'---Plasma TV---'
>>> y.strip('-')
'Plasma TV'
>>>

{% endhighlight %}

以上代码就成功删除开头和结尾的‘-’字符。

# 实例2 #


{% highlight ruby %}
#!/usr/bin/python3
str2 = "   bt699      ";   # 去除首尾空格
print(str2.strip());

{% endhighlight %}




# 输出 #
{% highlight ruby %}
bt699


{% endhighlight %}