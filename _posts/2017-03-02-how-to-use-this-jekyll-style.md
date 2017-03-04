---
layout: post
title:  如何使用Jekyll模板(2) - 配置样式、分类、标签
date:   2017-03-02 23:06:00 +0800
categories: Document
tag: Jekyll
---

* content
{:toc}

分类
------------------------------------

分类和标签功能是jekyll的`yaml-format`，`LessOrMore`的内置功能，在每篇文章上方可以设置：这里需要注意的是如果多个分类或者tag的话，用逗号分隔，并且要紧跟一个空格。分类可以任意添加，Jekyll在解析网站的时候会统计所有的分类，并放到site.categories中；换句话说，不能脱离文章而设置分类。

{% highlight bash %}
---
layout: default
title: Title
description: 这里的description是自定义属性。
categories: [web-build]
tags: [github-page, jekyll, liquid]
---
{% endhighlight %}
下面是本站罗列分类的代码，供大家参考

{% highlight bash %}
<div class='category'>
	<ul>
		{% for cat in site.categories %}
			<li><a href="{{ site.BASE_PATH }}/category.html#{{ cat[0] }}">{{ cat[0] }}<span>{{ cat[1].size }}</span></a></li>
		{% endfor %}
	</ul>
</div>
{% endhighlight %}

注意到分类的url链接，这里用了`hash`来实现。Tag的处理方式类似，这里就省略了。
推荐大家下载jekyll原作者推荐的简单例子来学习：

{% highlight bash %}
$ git clone https://github.com/plusjade/jekyll-bootstrap.git
{% endhighlight %}

Jekyll社区
------------------------------------
中文社区:[http://jekyll.com.cn/](http://jekyll.com.cn/)<br/>
英文社区:[http://jekyllrb.com/](http://jekyllrb.com/)  
 

 

 

 
