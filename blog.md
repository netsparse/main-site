---
layout: default
title: Blog
---
## Blog 
A colletion of my thoughts and writings. Feel free to browse around.

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