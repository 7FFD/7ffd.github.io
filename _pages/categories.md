---
layout: page
permalink: /categories/
title: Категорії
---


<div id="archives">
{% for category in site.categories %}
    {% capture category_name %}{{ category | first }}{% endcapture %}
    {% assign posts = site.categories[category_name] | where_exp:"item","item.hidden != 1" %}
    {% unless posts.size == 0 %}
  <div class="archive-group">
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    
    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in posts %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></h4>
    </article>
    {% endfor %}
  </div>
    {% endunless %}
{% endfor %}
</div>