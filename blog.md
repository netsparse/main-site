---
layout: default
title: Blog
---
## Blog 
A collection of my thoughts and posts. Feel free to browse around.

## Latest

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      · {{ post.date | date: "%b %d, %Y" }}
      <br>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>


[ < home](./)