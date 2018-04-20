---
layout: default
title: Blog
---
{% assign posts = site._blog | sort:"date" | reverse %}
{% for post in posts%}
<div>
    <a href="{{post.url}}"><h2>{{ post.title }}</h2></a>
    <p>
        <b>Written on {{ post.date | date: "%b %-d, %Y" }}, by Team Wombat</b>
        <br>
        {{ post.content | strip_html | truncatewords: 90}}
        <a style="float:right" href="{{post.url}}">Read more</a>
    </p>
</div>
{% endfor %}
