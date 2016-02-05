---
layout: page
title: Blog Archive
sidebar: "yes"
---

{% for post in site.posts  %}
  {% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}

  {% if forloop.first %}
###  {{this_year}}
    {% else %}
  {% if this_year != last_year %}
###  {{this_year}}
  {% endif %}
  {% endif %}

  * {{ post.date | date: '%B %-d' }} &raquo; [{{ post.title }}]({{ post.url }})

  {% if forloop.last %}
  {% endif %}

  {% capture last_year %}{{ this_year }}{% endcapture %}
{% endfor %}
