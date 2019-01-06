---
layout: post
title:  "python att-string-isdigit 方法!"
date:   2019-01-03 13:19:48 +0800
categories: python

---
# python isdigit() 方法  #
Python isdigit() 方法检测字符串是否只由数字组成

{% highlight ruby %}
str.isdigit()

{% endhighlight %}

如果字符串只包含数字则返回 True 否则返回 False。


# 实例1 #

{% highlight ruby %}
#!/usr/bin/python3
str = "123456";  # Only digit in this string
print(str.isdigit());

str = "this is string example....wow!!!";
print(str.isdigit());
{% endhighlight %}

# 实例2 #

{% highlight ruby %}
def filter_price(value):
    if value.isdigit():
        return value

{% endhighlight %}

# 输出 #
{% highlight ruby %}
True
False

{% endhighlight %}