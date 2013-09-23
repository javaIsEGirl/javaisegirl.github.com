---
layout: post
title: Ubuntu下Jekyll搭建博客时的代码高亮 
---

对于经常需要通过帖代码来说明问题的不帖代码会死星人来说，代码高亮是不可缺少的。
什么是代码高亮？为什么要使用代码高亮？代码高亮的方法有哪些？




![pygments_logo](http://start.ubuntu.com/12.04/sprite.pn)

##使用Pygments


此次我们关注的是通过pygments来实现博客中的代码高亮,具体步骤如下:

###	          A.安装pygments

{% highlight java linenos %}
$ sudo pacman -S python2-pygments
{% endhighlight %}

###	B.选择我们自己喜欢的代码高亮风格

####   1.![view_highlight_code ](http://image15-c.poco.cn/mypoco/myphoto/20130909/21/17406896920130909211221042.png)
####   2.![select_style](http://image15-c.poco.cn/mypoco/myphoto/20130909/21/17406896920130909211154085.png)
####   3.


### C.生成相应的.css文件

{% highlight java linenos %}
pygmentize -S default -f html > your/path/pygments.css
{% endhighlight %}

### D.引入生成好的.css文件到我们的网页

{% highlight java linenos %}
<link rel="stylesheet" href="/your/path/pygments.css">
{% endhighlight %}

### E.配置_config.yml文件

{% highlight java linenos %}
pygments: true
{% endhighlight %}

### F.如何使用

语法高亮的代码片段要放在标签对 \{ % highlight language % \} 和 \{ % endhighlight % \} 之间，其中的 language 为多种语言高亮页面中的 Short names。

###注意事项


##使用Javascript

