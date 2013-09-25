---
layout: post
title: Ubuntu下Jekyll搭建博客时的代码高亮 
---

对于经常需要通过帖代码来说明问题的不帖代码会死星人来说，代码高亮是不可缺少的。
什么是代码高亮？为什么要使用代码高亮？代码高亮的方法有哪些？


请参考 [Jekyll-Syntax highlighting](http://truongtx.me/2012/12/28/jekyll-bootstrap-syntax-highlighting/)

###使用Pygments
![pygments_logo](http://d3.freep.cn/170_3tb_130924174407k30h516640.png)

此次我们关注的是通过pygments来实现博客中的代码高亮,具体步骤如下:

#####1.安装pygments

{% highlight java linenos %}
$ sudo pacman -S python2-pygments
{% endhighlight %}

#####2.选择我们自己喜欢的代码高亮风格

a.写一段代码，为的是选择我们所喜欢的代码高亮风格:


![view_highlight_code ](http://d3.freep.cn/170_3tb_130924174408m512516640.png)


b.选择自己所喜欢的代码高亮风格，我选择的是monkai.css:


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

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx


#### 7.开始使用

语法高亮的代码片段要放在标签对 \{ % highlight language % \} 和 \{ % endhighlight % \} 之间，其中的 language 为多种语言高亮页面中的 Short names。
####注意事项 


###使用Javascript 

在jekyll中通过这种方式使代码高亮是非常简单的，因为它是自动完成的。这就意味着你不需要做任何事。一旦你包含了「highlight.js」脚本，它将自动为你识别代码块，检测语言并进行高亮显示。


####优势

易用 

易更新(只要替换js文件或甚至自动更新)


####劣势

效果并不是很好，但勉强接受

你不得不手动格式代代码块(缩进，换行)


####infomation

[highlight.js](http://softwaremaniacs.org/soft/highlight/en/)

[demo](http://softwaremaniacs.org/media/soft/highlight/test.html)

####Installation

Highlight.js的几种使用方式

首先，下载这个js文件，并将其解压至你的web站点目录下，并且将它包含进你的模板文件(usually/_includes/themes/theme-name/default.html).记得编辑链接到正确的位置。


{% highlight html linenos %}
<link rel="stylesheet" href="styles/default.css">
<script src="highlight.pack.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
{% endhighlight %}


另一种方法「更快」，「更简单」.Highlight.js托管在[Yandex]()上，所以你甚至不用下载和安装js文件，只需要将它包含在你的模板文件中(usually/_includes/themes/theme-name/default.html),然后，


{% highlight html linenos %}
<link rel="stylesheet" href="http://yandex.st/highlightjs/7.3/styles/default.min.css">
<script src="http://yandex.st/highlightjs/7.3/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
{% endhighlight %}




