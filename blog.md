---
layout: page
title: Blog
permalink: /blog/
---

Blog

<ul>
{% for post in site.posts %}
{% if post.category contains 'blog' 
%}
 <li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endif %}
{% endfor %}
</ul>
