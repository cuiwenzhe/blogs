---
layout: page
---

{% for post in site.posts %}
{% if post.categories[0] == 'photo' %}
    <a href="{{ post.url | absolute_url }}">
      {{ post.title }}
	{{post.categories}}
    </a>
{% endif %}
{% endfor %}
