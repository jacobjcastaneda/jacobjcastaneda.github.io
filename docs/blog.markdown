---
title: Blog
layout: page
---

{% for post in site.posts %}

   <a href="{{site.url}}{{site.baseurl}}{{post.url}}">{{post.title}}</a>

{% endfor %}


