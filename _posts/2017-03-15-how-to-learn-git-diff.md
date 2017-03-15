---
layout: post
title: Git查看某个版本修改了哪些文件
date:   2017-03-15 23:46:00 +0800
categories: Tutorial
tag: Git
 
---

* content
{:toc}

查看某个版本提交了哪些文件，其实就是查看该版本与其上一个版本之间的差异，所以通过 git diff 命令来取得结果，并且对比的是要查看的版本与它的上一个版本的 commit 号。
 
{% highlight bash %}
git diff hash1 hash2 --stat
{% endhighlight %}
 
>如果不加上 --stat 参数会显示每个文件内容的两个版本之间的差异，加上该参数后就只显示发生变更的文件名了。

如果是branch的话:
{% highlight bash %}
git diff branch1 branch2 --stat
{% endhighlight %}
>加上 --stat 是显示文件列表, 否则是文件内容diff

 