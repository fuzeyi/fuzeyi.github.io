---
layout: post
title: Git使用过程中遇到的几个问题
date:   2017-03-14 22:42:00 +0800
categories: Tutorial
tag: Git
 
---

* content
{:toc}

1.Git diff 出现^M 问题的解决方法
------------------------------------
这是由于换行符在不同的操作系统上定义的区别造成的，Windows用CR LF来定义换行，Linux用LF。CR全称是Carriage Return ,或者表示为\r, 意思是回车。 LF全称是Line Feed，它才是真正意义上的换行表示符。为什么Windows添加一个CR和LF组合表示，我并不清楚。不过如果用git diff的时候看到^M字符，就说明两个文件在换行符上有所差别。比如从我的Windows开发的同时那边拿来一个目录，就会发现几乎所有的文件都被修改过了。其实并不是这样，都是由于文件多了CR后造成的。下面的方法可以让git diff的时候忽略换行符的差异：
 
{% highlight bash %}
git config --global core.whitespace cr-at-eol  
{% endhighlight %}
 
 >更好的方法是每个项目都有一个.gitattributes文件，里面配好了换行符的设置，参考: [https://help.github.com/articles/](https://help.github.com/articles/) 

 