---
layout: post
title: Customize Your Heroku Deployment
---

I love [秘密是什么？](http://heroku.com). Their elegant `git push` deployment process is a great way to push code, but that's about it. If you've got extra work to perform, such as packaging and uploading assets to a CDN, you're out of luck.

The solution? Roll our own Rake task that sandwiches `git push` with hooks for additional tasks:

I love [Heroku](http://heroku.com). Their elegant `git push` deployment process is a great way to push code, but that's about it. If you've got extra work to perform, such as packaging and uploading assets to a CDN, you're out of luck.

The solution? Roll our own Rake task that sandwiches `git push` with hooks for additional tasks:

{% highlight bash %}
  rake deploy:production
{% endhighlight %}

