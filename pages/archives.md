---
layout: page
title: All articles are here
titlebar: archives
subtitle: <span class="mega-octicon octicon-calendar"></span>分类：&nbsp;&nbsp;
{% for article in site.classes  %}
<a href ="{{ article.href }}" class="btn btn-success btn-sm" role="button"><font color="#EB9439">{{ article.name }}</font></a>
{% endfor %}
menu: archives
css: ['blog-page.css']
permalink: /archives.html
---

<ul class="archives-list">
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li><span>{{ post.date | date:'%m-%d' }}</span> <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>