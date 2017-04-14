---
layout: post
title:  如何使用Jekyll模板(4) - 安装异常处理
date:   2017-04-13 21:57:00 +0800
categories: Document
tag: Jekyll
---

* content
{:toc}


In Jekyll 3, pagination is deprecated. This post describes how to resolve the error: “Deprecation: You appear to have pagination turned on, but you haven’t included the jekyll-paginate gem. Ensure you have gems: [jekyll-paginate] in your configuration file.”

{% highlight ruby lineno %}

First, make sure you have the gem installed by typing in your terminal: gem install jekyll-paginate
Next, open _config.yml, add add the following line:

gems :
  - jekyll-paginate

{% endhighlight %}
 
 
 

 

 

 
