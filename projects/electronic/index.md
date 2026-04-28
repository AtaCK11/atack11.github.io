---
layout: default
title: RF Projects
---

<section class="projects-hero">
  <h2>Electronics</h2>
  <p>Hardware builds.</p>
</section>

<section class="projects-grid">

{% assign pages_with_date = site.pages | where_exp: "p", "p.date != nil" %}
{% assign pages_sorted = pages_with_date | sort: "date" | reverse %}
{% for post in pages_sorted %}
  {% if post.layout == "post" and post.path contains "projects/electronic/" %}
  <a class="project-card electronic" data-label="{{ post.date | date: '%Y-%m-%d' }}" href="{{ post.url }}">
    <h3>{{ post.title }}</h3>
    <p>
      {% if post.tags %}
        {% for tag in post.tags %}
          #{{ tag }}
        {% endfor %}
      {% endif %}
    </p>
  </a>
  {% endif %}
{% endfor %}

</section>
