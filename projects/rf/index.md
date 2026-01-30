---
layout: default
title: RF Projects
---

# RF Projects

{% assign rf_pages = site.pages | where_exp: "p", "p.path contains 'projects/rf/' and p.layout == 'post'" | sort: "date" | reverse %}

{% for post in rf_pages %}
- **[{{ post.title }}]({{ post.url }})**  
  <small>{{ post.date | date: "%Y-%m-%d" }}</small>
{% endfor %}
