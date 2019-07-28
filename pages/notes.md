---
layout: page
title: 生活工作随笔
titlebar: notes
subtitle: <span class="mega-octicon octicon-clippy"></span>&nbsp;&nbsp; 在路上，不为旅行，不因某人，只为在未知的途中遇见未知的自己。
menu: notes
css: ['blog-page.css']
permalink: /notes
---

<div class="row">

    <div class="col-md-12">
    
        <ul id="posts-list">
            {% for post in site.tags.notes %}
                <li class="posts-list-item">
                    <div class="posts-content">
                        <span class="posts-list-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
                        <a class="posts-list-name bubble-float-left" href="{{ site.url }}{{ post.url }}">{{ post.title }}</a>
                        <span class='circle'></span>
                    </div>
                </li>
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