---
layout: page
title: 架构师之路
titlebar: arch
subtitle: <span class="mega-octicon octicon-organization"></span>&nbsp;&nbsp; 架构师的修养
menu: arch
css: ['blog-page.css']
permalink: /arch
---

<div class="row">

    <div class="col-md-12">

        <ul id="posts-list">
            {% for post in site.tags.arch %}
				{% if post.category=='tech' %}
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