---
layout: page
title: About Me
menu: about
subtitle:   <section class="jumbotron">
    <div class="container">
        <h1>{{ site.title }}</h1>
        <div id="jumbotron-meta-info">
            <span class="meta-info">
                <span class="octicon octicon-location"></span>
                {{ site.location }}
            </span>
            <span class="meta-info hvr-grow">
                <span class="octicon octicon-organization"></span>
                <a href="{{ site.company_url }}" target="_blank">{{ site.company }}</a>
            </span>
            <span class="meta-info hvr-grow">
                <span class="octicon octicon-mark-github"></span>
                <a href="{{ site.github_url }}" target="_blank">@{{ site.name }}</a>
            </span>
        </div>
    </div>
</section>
                            
css: ['about.css', 'sidebar-popular-repo.css', '../../bower_components/flag-icon-css/css/flag-icon.min.css']
---

{% include about.html %}