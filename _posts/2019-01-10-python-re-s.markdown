---
layout: post
title:  "python re s!"
date:   2019-01-10 13:19:48 +0800
categories: re

---
# python re s() 方法  #
有一个参数为re.S。它表示跨行匹配。将“\n”当做一个普通的字符加入到这个字符串中，在整体中进行匹配

# 实例1 #

{% highlight ruby %}
>>> import re
>>> x = '''asdfbtopecs:
	123
	699af
	'''
>>> y = re.findall('bt(.*?)699',x)
>>> y
[]
>>> z = re.findall('bt(.*?)699',x,re.S)
>>> z
['opecs:\n\t123\n\t']
>>> 
{% endhighlight %}



如果不使用re.S参数，则只在每一行内进行匹配，如果一行没有，就换下一行重新开始，不会跨行。而使用re.S参数以后，正则表达式会将这个字符串作为一个整体，将“\n”当做一个普通的字符加入到这个字符串中，在整体中进行匹配。

