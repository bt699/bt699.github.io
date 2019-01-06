---
layout: post
title:  " jekyll serve报错分析"
date:   2019-01-05 13:19:48 +0800
categories:  jekyll
---
# jekyll serve报错分析 #

在Win10系统上按官方教程安装jekyll后运行jekyll serve报错分析刚安装完打开一个文件时报错：
{% highlight ruby %}
Traceback (most recent call last):
        5: from C:/Ruby25-x64/bin/jekyll:23:in `<main>'
        4: from C:/Ruby25-x64/bin/jekyll:23:in `load'
        3: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/jekyll-3.8.5/exe/jekyll:11:in `<top (required)>'
        2: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/jekyll-3.8.5/lib/jekyll/plugin_manager.rb:48:in `require_from_bundler'
        1: from C:/Ruby25-x64/lib/ruby/2.5.0/rubygems/core_ext/kernel_require.rb:59:in `require'
C:/Ruby25-x64/lib/ruby/2.5.0/rubygems/core_ext/kernel_require.rb:59:in `require': cannot load such file -- bundler (LoadError)
{% endhighlight %}
判断是因为缺少bundler组件，安装后gem install jekyll bundler
{% highlight ruby %}
Successfully installed jekyll-3.8.5
Parsing documentation for jekyll-3.8.5
Done installing documentation for jekyll after 3 seconds
Fetching: bundler-1.17.3.gem (100%)
Successfully installed bundler-1.17.3
Parsing documentation for bundler-1.17.3
Installing ri documentation for bundler-1.17.3
Done installing documentation for bundler after 20 seconds
2 gems installed
{% endhighlight %}
再次运行，结果错误更多了
{% highlight ruby %}
Traceback (most recent call last):
        15: from C:/Ruby25-x64/bin/jekyll:23:in `<main>'
        14: from C:/Ruby25-x64/bin/jekyll:23:in `load'
        13: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/jekyll-3.8.5/exe/jekyll:11:in `<top (required)>'
        12: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/jekyll-3.8.5/lib/jekyll/plugin_manager.rb:50:in `require_from_bundler'
        11: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler.rb:107:in `setup'
        10: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/runtime.rb:20:in `setup'
         9: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/runtime.rb:108:in `block in definition_method'
         8: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/definition.rb:226:in `requested_specs'
         7: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/definition.rb:237:in `specs_for'
         6: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/definition.rb:170:in `specs'
         5: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/definition.rb:258:in `resolve'
         4: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/resolver.rb:22:in `resolve'
         3: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/resolver.rb:49:in `start'
         2: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/resolver.rb:255:in `verify_gemfile_dependencies_are_found!'
         1: from C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/resolver.rb:255:in `each'
C:/Ruby25-x64/lib/ruby/gems/2.5.0/gems/bundler-1.17.3/lib/bundler/resolver.rb:287:in `block in verify_gemfile_dependencies_are_found!': Could not find gem 'tzinfo-data x64-mingw32' in any of the gem sources listed in your Gemfile. (Bundler::GemNotFound)
{% endhighlight %}

继续安装：
{% highlight ruby %}
gem install tzinfo-data x64-mingw32
Fetching: tzinfo-data-1.2018.9.gem (100%)
Successfully installed tzinfo-data-1.2018.9
Parsing documentation for tzinfo-data-1.2018.9
Installing ri documentation for tzinfo-data-1.2018.9
Done installing documentation for tzinfo-data after 1 seconds
ERROR:  Could not find a valid gem 'x64-mingw32' (>= 0) in any repository
1 gem installed
{% endhighlight %}
问题依旧，后来在上级目录运行E:\gitwenjian>jekyll serve

竟然成功运行了
{% highlight ruby %}
Server address: http://127.0.0.1:4000/
Server running... press ctrl-c to stop.
{% endhighlight %}
经过仔细比对发现，两个目录唯一区别在于没有/.git/目录，问题终于锁定。

解决办法就是：输入git init 命令

jekyll serve报错先要排查运行过git init 命令没


