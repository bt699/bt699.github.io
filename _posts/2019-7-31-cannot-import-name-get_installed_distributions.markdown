---
layout: post
title:  "cannot import name 'get_installed_distributions"
date:   2019-07-31 13:19:48 +0800
categories: pip

---
# cannot import name 'get_installed_distributions'#
module 'pip' has no attribute 'get_installed_distributions'。

# 实例1 #

{% highlight ruby %}
x10 = pip.get_installed_distributions()
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
<ipython-input-2-bbaa3f8c885b> in <module>
----> 1 x10 = pip.get_installed_distributions()

AttributeError: module 'pip' has no attribute 'get_installed_distributions'
{% endhighlight %}
# 完美代码 #

{% highlight ruby %}
import numpy as np
import scipy as sp
import pandas as pd
import pip
from pip._internal.utils.misc import get_installed_distributions


x10=pip._internal.utils.misc.get_installed_distributions()
df=pd.DataFrame();
df['name']=x10
print(df.head())

df.to_csv('tmp/m10.csv',index=False)


{% endhighlight %}

{% highlight ruby %}
runfile('E:/zwPython/py36/py_demo/3-3.py', wdir='E:/zwPython/py36/py_demo')
                        name
0                 3to2 1.1.1
1       zope.interface 4.6.0
2                  zmq 0.0.0
3              zipline 1.3.0
4  zipline-cn-databundle 0.5
{% endhighlight %}


pip的get_installed_distributions属性已经报错，转移到
#from pip._internal.utils.misc import get_installed_distributions。

