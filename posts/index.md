---
layout: default
title: Blog
---

# Blog

{% assign blog_posts = site.pages | where_exp: "page", "page.layout == 'post'" | sort: "date" | reverse %}

{% if blog_posts.size > 0 %}
<ul class="post-list">
{% for post in blog_posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    {% if post.date %}
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
    {% endif %}
  </li>
{% endfor %}
</ul>
{% else %}
<p>No posts yet.</p>
{% endif %}
