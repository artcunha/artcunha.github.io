---
layout: page
title: Tech Art
logo: logoblack
permalink: /techart

---
 
<div>

{% for post in site.posts %}
{% if post.category contains 'techart' 
%}
    {% cycle 'add row' : '<div class="row">', '', '' %}
        <div class="column column-33">
            <div class="preview-panel">
                <a href="{{ post.url | prepend: site.baseurl }}">
                    <img src="{{ post.preview }}">
                </a>
                <div class="post-title">{{ post.title }}</div>
               {% if post.tagmerit %}
                <a href="#" class="tag" style="font-size: 9px;">{{post. tagmerit}}</a>
                {% endif %}
           </div>
        </div>
{% cycle 'end row' : '', '', '</div>' %}
{% endif %}
{% endfor %}
{% cycle 'end row' : '', '</div>', '</div>' %}
</div>
