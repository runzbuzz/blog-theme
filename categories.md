---
layout: default
permalink: /categories
title: Categories
---

<style>
div:target h2{
  background: #009fe3;
  border-radius: 5px;
  color: #fff;
  max-width: max-content
  -webkit-text-stroke: 3px #007bbd;

} 
  
</style>

{% assign sorted_categories = site.categories | sort %}
{% for category in sorted_categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="{{ category_name | slugize }}">
        <h2>{{ category_name }}</h2>
        <ul>
          {% for post in site.categories[category_name] %}
            <li><a class="archive-link" href="{{ post.url | absolute_url}}">{{post.title}}</a></li>
          {% endfor %}
        </ul>
    </div>
  </div>
{% endfor %}
