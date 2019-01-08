---
layout: post
title:  "python re compile!"
date:   2019-01-09 13:19:48 +0800
categories: re

---
# python re compile() 方法  #
Python re compile() 使用re.compile()函数进行转换后，re.search(pattern, string)的调用方式就转换为 pattern.search(string)的调用方式。

# 实例1 #

{% highlight ruby %}
>>> import re
>>> some_text = 'a,b,,,,c d'
>>> re1 = re.compile('[, ]+'，some_text)
SyntaxError: invalid character in identifier
>>> re1 = re.compile('[, ]+',some_text)
Traceback (most recent call last):
  File "<pyshell#13>", line 1, in <module>
    re1 = re.compile('[, ]+',some_text)
  File "C:\Users\zrt\AppData\Local\Programs\Python\Python37\lib\re.py", line 234, in compile
    return _compile(pattern, flags)
  File "C:\Users\zrt\AppData\Local\Programs\Python\Python37\lib\re.py", line 286, in _compile
    p = sre_compile.compile(pattern, flags)
  File "C:\Users\zrt\AppData\Local\Programs\Python\Python37\lib\sre_compile.py", line 764, in compile
    p = sre_parse.parse(p, flags)
  File "C:\Users\zrt\AppData\Local\Programs\Python\Python37\lib\sre_parse.py", line 930, in parse
    p = _parse_sub(source, pattern, flags & SRE_FLAG_VERBOSE, 0)
TypeError: unsupported operand type(s) for &: 'str' and 'int'
>>> re1 = re.compile('[, ]+')
>>> re1.findall(some_text)
[',', ',,,,', ' ']
>>> re2 = re.compile('\d+')
>>> re2.findall(some_text)
[]
>>> re3 = re.compile('\s+')
>>> re3.findall(some_text)
[' ']
>>> re4 = re.compile('\s+')
>>> re4 = re.compile('\w+')
>>> re4.findall(some_text)
['a', 'b', 'c', 'd']
{% endhighlight %}

以上代码指定正则'\w' 匹配单词字符等同于[A-Za-z0-9] 

