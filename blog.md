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
{% endfor %}
</ul>

<!-- 
<div style="clear: both;">
  <div style="float: left; margin-right 1em;">
    <img src="/assets/img/profile.jpg" alt="" width=400>
  </div>
  <div style="margin-left 2em;">
    <h2>About</h2>
    <p>
    My background in design informs everything I do. <br>
    I enjoy learning new crafts and collaborating with artists! <br><br>
    Currently working at Sony Pictures Imageworks <br>
    </p>
  </div>
</div> -->