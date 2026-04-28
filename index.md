---
layout: home
title: Home
---

Hi, I'm **Atabit**.

I work on embedded systems, electronics, and RF-related projects.

This site is a collection of things I've built, tested, and learned.

---

<p><strong>Visit My Projects</strong></p><a href="/projects/" class="terminal-link">user@site:~$ ./projects</a>

---

### Recent

<div class="recent-posts">
{%- assign all_posts = site.pages | where_exp: "p", "p.date != nil" -%}
{%- assign posts_a = all_posts | where: "layout", "post" -%}
{%- assign posts_b = all_posts | where: "layout", "blog-post" -%}
{%- assign all_posts = posts_a | concat: posts_b -%}
{%- assign all_posts = all_posts | sort: "date" | reverse -%}
{%- for post in all_posts limit:5 -%}
  {%- assign parts = post.path | split: "/" -%}
  {%- assign category = parts[1] -%}
  <a class="recent-post-item" href="{{ post.url }}">
    <span class="recent-post-category {{ category }}">{{ category }}</span>
    <span class="recent-post-title">{{ post.title }}</span>
    <span class="recent-post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
  </a>
{%- endfor -%}
</div>

---

### Areas of interest

- Embedded systems
- Circuit design
- RF &amp; antennas
- Low-level programming
