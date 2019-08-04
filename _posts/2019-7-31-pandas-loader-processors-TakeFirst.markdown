---
layout: post
title:  "random shuffle"
date:   2019-07-30 13:19:48 +0800
categories: random

---
# random shuffle#
对原列表打乱顺序。

# 实例1 #

{% highlight ruby %}
>>> random.shuffle
<bound method Random.shuffle of <random.Random object at 0x000001CD9C5C59E8>>
{% endhighlight %}
# 实例2 #
{% highlight ruby %}
>>> l1 = list(range(1,13))
>>> l1
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
>>> random.shuffle(l1)
Traceback (most recent call last):
  File "<pyshell#2>", line 1, in <module>
    random.shuffle(l1)
NameError: name 'random' is not defined
>>> import random
>>> random.shuffle(l1)
>>> l1
[12, 6, 1, 8, 5, 10, 3, 2, 4, 7, 11, 9]
>>> 


{% endhighlight %}

# 实例3 多次使用shuffle方法 #
{% highlight ruby %}
>>> random.shuffle(l1)
>>> l1
[12, 6, 1, 8, 5, 10, 3, 2, 4, 7, 11, 9]
>>> random.shuffle(l1)
>>> l1
[1, 12, 10, 5, 8, 4, 6, 3, 11, 9, 2, 7]
>>> 
{% endhighlight %}

random中的shuffle方法，是对原列表进行随机排序的。可以多次使用。

