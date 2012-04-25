---
layout: post
title: Archive
categories:
---

<h2>Archives</h2>
<ul>
{% for post in site.posts %}
{% capture the_year %}
{{ post.date|date:"%Y" }}
{% endcapture %}
{% capture previous_year %}
{{ previous_post.date|date:"%Y" }}
{% endcapture %}

{% if the_year != previous_year %}
{% assign year_changed = true %}
{% else %}
{% assign year_changed = false %}
{% endif %}
{% if year_changed %}
<li><a href="{{ site.url }}/archives/{{the_year}}.html">{{ the_year }}</a></li>
{% endif %}
{% assign previous_post = post %}
{% endfor %}
</ul>