---
layout: page
title: 美食
titlebar: delicacy
subtitle: <span class="mega-octicon octicon-flame"></span>&nbsp;&nbsp; 下厨本身并不是一件新鲜时髦的事，在端出来的食物背后，需要的是事无巨细的耐心对待，承受必定会发生的烫伤和刀伤，特别还要懂得及时打扫和清洁，以及接受失败。等等这些都是真实的意义，不浪漫也不潇洒。
menu: delicacy
css: ['blog-page.css']
permalink: /delicacy
keywords: delicacy
---

<div class="row">

    <div class="col-md-12">

        <ul id="posts-list">
            {% for post in site.posts %}
                {% if post.category=='delicacy'  or post.keywords contains 'delicacy' %}
                <li class="posts-list-item">
                    <div class="posts-content">
                        <span class="posts-list-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
                        <a class="posts-list-name bubble-float-left" href="{{ site.url }}{{ post.url }}">{{ post.title }}</a>
                        <span class='circle'></span>
                    </div>
                </li>
                {% endif %}
            {% endfor %}
        </ul> 

        <!-- Pagination -->
        {% include pagination.html %}

        <!-- Comments -->
       <div class="comment">
         {% include comments.html %}
       </div>
    </div>

</div>
<script>
    $(document).ready(function(){

        // Enable bootstrap tooltip
        $("body").tooltip({ selector: '[data-toggle=tooltip]' });

    });
</script>