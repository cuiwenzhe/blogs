---
layout: page
title: 故事
---
<ul class="posts">
  {% for post in site.posts %}
   {% if post.category == 'story' %}
    {% assign words = post.content | strip_html | number_of_words %}
     {% if words >= 200 %}
      {{ post.content | strip_html | truncate: 200 }} 
	<a href="{{ site.github.url }}{{ post.url }}">>>></a>
     {% else %}
      {{ post.content }} 
    <li itemscope>
      <a href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
      <p class="post-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ post.date | date: "%B %-d" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</span></p>
    </li>
    {% endif %}
   {% endif %}
  {% endfor %}
</ul>
