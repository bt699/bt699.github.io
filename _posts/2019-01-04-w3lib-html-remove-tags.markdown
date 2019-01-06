---
layout: post
title:  "w3lib html remove tags 方法!"
date:   2019-01-04 13:19:48 +0800
categories: python

---
# remove_tags() 方法  #
remove_tags 去除html的标签

{% highlight python %}
>>> from w3lib.html import remove_tags
>>> remove_tags(u'<span>1000</span>')
'1000'
>>> remove_tags('<span>1000</span>')
'1000'
>>> remove_tags(u'<strong>website</strong>')
'website'
>>> 
{% endhighlight %}


removetags.py
{% highlight python %}
x = '''
<div class="bd" id="pageNo-12" data-page-no="12" data-mate-width="892.979" data-mate-height="1262.879" style="height: 1343.66px;" data-scale="0.70709782964164" data-render="1"><div class="reader-parent-ecbc286c8e9951e79b8927ec reader-parent " style="position:relative;top:0;left:0;-webkit-transform:scale(1.00);-webkit-transform-origin:left top;"><div class="reader-wrapecbc286c8e9951e79b8927ec" style="position:absolute;top:0;left:0;width:100%;height:100%;"><div class="reader-main-ecbc286c8e9951e79b8927ec" style="position:relative;top:0;left:0;width:100%;height:100%;"><div class="reader-txt-layer" style="z-index:1"><div class="ie-fix"><p class="reader-word-layer reader-word-s12-1" style="width:1207px;height:241px;line-height:241px;top:762px;left:685px;z-index:0;false">热闹—冷清</p>
</p></div></div></div></div></div></div>
'''
from w3lib.html import remove_tags
print(remove_tags(x))
{% endhighlight %}

# 输出 #
IDLE选择菜单Run 再选择 Run Module
{% highlight python %}
=======

热闹—冷清


>>> 
{% endhighlight %}


