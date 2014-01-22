---
layout: page
permalink: /articles/
title: Artigos
description: "Um arquivo de posts ordenados por data."
---

<ul class="post-list">
{% for post in site.posts %} 
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d/%m/%Y" }}</time></span></a></article></li>
{% endfor %}
</ul>
