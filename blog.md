---
layout: default
title: Blog
---

# Our Blog

{% assign posts = site._blog | sort:"date" | reverse %}
{% for post in posts%}
<div>
    <a href="{{post.url}}"><h2>{{ post.title }}</h2></a>
    <b>{{ post.date | date: "%b %-d, %Y" }}</b> <br><br>
    <p>{{ post.content | strip_html | truncatewords: 30}}</p>
</div>
{% endfor %}
