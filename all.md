---
title: 极简设计
layout: default
---

<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% capture m %}{{post.date | date:"%m"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator">{{ y }}</li>
  {% endif %}
       {% if month != m %}
            {% assign month = m %}
              <li class="listing-seperator">{{ m }} 月</li>
       {% endif %}
  <li class="listing-item">
    {{ post.date | date:"%d" }}
    <a href="{{ site.url }}/{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>

