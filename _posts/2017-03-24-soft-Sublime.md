---
layout: post
title: Sublime安装和插件安装
date:   2017-03-24 19:45:00 +0800
categories: Soft
tag: Tool
---

* content
{:toc}

1.下载及安装emmet插件
------------------------------------
首先去Sublime官网下载软件：[http://www.sublimetext.com/](http://www.sublimetext.com/)

2.package control组件的安装
------------------------------------
软件安装好了之后，我们来安装一个插件，推荐使用package control组件来安装插件，很方便。安装方法如下： 按快捷键ctrl+~ 调出命名控制行, 
如果是text2输入如下命令：
 
 >import urllib2,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')

如果是text3输入如下命令：
>import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)

具体安装您也可以查看：[https://sublime.wbond.net/installation#st3](https://sublime.wbond.net/installation#st3)


3.Sublime常用插件安装
------------------------------------
**Emmet**
{% highlight bash %}
打开package control 输入install package 然后找到emmet，点击安装，重启sublime就可以了。
{% endhighlight %}

**ZenCoding**
{% highlight  bash%}
不得不用的一款前端开发方面的插件，Write less , show more.安装后可直接使用，Tab键触发，Alt+Shift+W是个代码机器。
{% endhighlight %}

**Alignment**
{% highlight  bash%}
代码对齐，如写几个变量，选中这几行，Ctrl+Alt+A 
{% endhighlight %}

**Prefixr**
{% highlight  bash%}
写 CSS可自动添加 -webkit 等私有词缀，Ctrl+Alt+X触发
{% endhighlight %}


**Tag**
{% highlight  bash%}
Html格式化，右键Auto-Format Tags on Ducument。一般是用ctrl +Alt +F 触发，若触发不了，查看是不是html文件，是否选中，是否有快捷键冲突！
{% endhighlight %}

**Ctags**
{% highlight  bash%}
函数跳转，我的电脑上是Alt+点击 函数名称，会跳转到相应的函数
{% endhighlight %}

**Clipboard History**
{% highlight  bash%}
剪贴板历史记录，显示更多历史复制，Ctrl+Shift+V触发。
{% endhighlight %}

**SideBarEnhancements**
{% highlight  bash%}
侧栏右键功能增强，非常实用
{% endhighlight %}

**Theme – Soda**
{% highlight  bash%}
完美的编码主题，用过的都说好，Setting user里面添加”theme”: “Soda Dark.sublime-theme”
{% endhighlight %}

**GBK to UTF8**
{% highlight  bash%}
将文件编码从GBK转黄成UTF8，菜单 – File里面找
{% endhighlight %}

**SFTP**
{% highlight  bash%}
直接编辑 FTP 或 SFTP 服务器上的文件，绝对FTP浮云
{% endhighlight %}

**WordPress**
{% highlight  bash%}
集成一些WordPress的函数，对于像我这种经常要写WP模版和插件的人特别有用
{% endhighlight %}

**PHPTidy**
{% highlight  bash%}
整理排版PHP代码
{% endhighlight %}


**YUI Compressor**
{% highlight  bash%}
压缩JS和CSS文件
{% endhighlight %}

**Doc​Blockr**
{% highlight  bash%}
注释插件，生成幽美的注释。标准的注释，包括函数名、参数、返回值等，并以多行显示，省去手动编写
{% endhighlight %}

**Ftpsync**
{% highlight  bash%}
FTP ssh上传配置，安装成功配置一下host等就可以了！
{% endhighlight %}

**ConvertToUTF8**
{% highlight  bash%}
可以解决Sublime Text 在GBK编码下的中文乱码问题！
{% endhighlight %}

4.Sublime常见问题解决方案
------------------------------------
**Sublime中文文件名显示乱码**

>在sublime text 3中，打开Preference -> Settings，在文件最后加上一行：
"dpi_scale": 1.0
{% highlight bash %}
例如：
{
"font_face": "Consolas",
"font_size": 15,
"ignored_packages":
[
"Vintage"
],
"line_padding_bottom": 1,
"line_padding_top": 1,
"tab_size": 4,
"translate_tabs_to_spaces": true,
"word_wrap": "true",
"dpi_scale": 1.0 #主要是这行生效！
}
{% endhighlight %}