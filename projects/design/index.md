---
layout: default
title: RF Projects
---

<section class="projects-hero">
  <h2>PCB Design</h2>
  <p>Power, analog, controller PCB designs.</p>
</section>

<section class="projects-grid">

{% assign pages_sorted = site.pages | sort: "date" | reverse %}
{% for post in pages_sorted %}
  {% if post.layout == "post" and post.path contains "projects/design/" %}
  <a class="project-card design" data-label="{{ post.date | date: '%Y-%m-%d' }}" href="{{ post.url }}">
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
