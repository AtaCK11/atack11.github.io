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

### Recent Projects

<div class="recent-posts">
{%- assign projects = site.pages | where: "layout", "post" -%}
{%- assign projects = projects | where_exp: "p", "p.date != nil" -%}
{%- assign projects = projects | sort: "date" | reverse -%}
{%- for post in projects limit:4 -%}
  {%- assign parts = post.path | split: "/" -%}
  {%- assign category = parts[1] -%}
  <a class="recent-post-item" href="{{ post.url }}">
    <span class="recent-post-category {{ category }}">{{ category }}</span>
    <span class="recent-post-title">{{ post.title }}</span>
    <span class="recent-post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
  </a>
{%- endfor -%}
</div>

### Recent Blog Posts

<div class="recent-posts">
{%- assign blogposts = site.pages | where: "layout", "blog-post" -%}
{%- assign blogposts = blogposts | where_exp: "p", "p.date != nil" -%}
{%- assign blogposts = blogposts | sort: "date" | reverse -%}
{%- for post in blogposts limit:4 -%}
  {%- assign parts = post.path | split: "/" -%}
  {%- assign category = parts[1] -%}
  {%- assign parent_path = parts[0] | append: "/" | append: parts[1] | append: "/" | append: parts[2] | append: "/index.md" -%}
  {%- assign parent = site.pages | where: "path", parent_path | first -%}
  <a class="recent-post-item" href="{{ post.url }}">
    <span class="recent-post-category {{ category }}">{{ category }}</span>
    <span class="recent-post-title">
      {{ post.title }}
      {%- if parent -%}
        <span class="recent-post-parent">in {{ parent.title }}</span>
      {%- endif -%}
    </span>
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
