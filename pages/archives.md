---
layout: page
title: All articles are here
titlebar: archives
subtitle: <span class="mega-octicon octicon-calendar"></span>分类：&nbsp;&nbsp; <a href ="/tech" class="btn btn-success btn-sm" role="button">技术</a>&nbsp;&nbsp;<a href ="/trival" class="btn btn-success btn-sm" role="button">旅游</a>&nbsp;&nbsp;<a href ="/delicacy" class="btn btn-success btn-sm" role="button">美食</a>&nbsp;&nbsp;<a href ="/collection" class="btn btn-success btn-sm" role="button">资源收藏</a>
menu: archives
css: ['blog-page.css']
permalink: /archives
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