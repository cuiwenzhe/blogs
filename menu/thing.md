---
layout: page
title: 玩意儿
---
<ul class="posts">
{% for post in site.posts %}
{% if post.category == 'thing' %}
<h1>
<a href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
</h1>
{% assign words = post.content | strip_html | number_of_words %}
{% if words >= 200 %}
{{ post.content | strip_html | truncate: 200 }} 
<a href="{{ site.github.url }}{{ post.url }}">>>></a>
{% else %}
{{ post.content }} 
<li itemscope>
<p class="post-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ post.date | date: "%B %-d" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</span></p>
</li>
{% endif %}
{% endif %}
{% endfor %}
</ul>
