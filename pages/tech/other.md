---
layout: page
title: 杂七杂八的技术
titlebar: spring-cloud
subtitle: <span class="mega-octicon octicon-organization"></span>&nbsp;&nbsp; 杂七杂八的技术
menu: other
css: ['blog-page.css']
permalink: /other
---

<div class="row">

    <div class="col-md-12">

        <ul id="posts-list">
            {% for post in site.tags.other %}
				{% for post.category=='tech' %}
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