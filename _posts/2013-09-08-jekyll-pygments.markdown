---
layout: post
title: Ubuntu下Jekyll搭建博客时的代码高亮 
---

对于经常需要通过帖代码来说明问题的不帖代码会死星人来说，代码高亮是不可缺少的。
什么是代码高亮？为什么要使用代码高亮？代码高亮的方法有哪些？

###使用Pygments
![pygments_logo](http://d3.freep.cn/170_3tb_130924174407k30h516640.png)

此次我们关注的是通过pygments来实现博客中的代码高亮,具体步骤如下:

#####1.安装pygments

{% highlight java linenos %}
$ sudo pacman -S python2-pygments
{% endhighlight %}

#####2.选择我们自己喜欢的代码高亮风格

######  a.写一段代码，为的是选择我们所喜欢的代码高亮风格:


![view_highlight_code ](http://d3.freep.cn/170_3tb_130924174408m512516640.png)
######  b.选择自己所喜欢的代码高亮风格，我选择的是monkai.css:


![select_style](http://d3.freep.cn/170_3tb_1309241744095jjv516640.png)


#####3.通过下面的命令，生成相应的.css文件
{% highlight java linenos %}
pygmentize -S default -f html > your/path/pygments.css
{% endhighlight %}

#### 4.引入生成好的.css文件到我们的网页

{% highlight java linenos %}
<link rel="stylesheet" href="/your/path/pygments.css">
{% endhighlight %}

#### 5.配置_config.yml文件

{% highlight java linenos %}
pygments: true
{% endhighlight %}

#### 6.参数的设置




#### 7.开始使用

语法高亮的代码片段要放在标签对 \{ % highlight language % \} 和 \{ % endhighlight % \} 之间，其中的 language 为多种语言高亮页面中的 Short names。

####注意事项


###使用Javascript

