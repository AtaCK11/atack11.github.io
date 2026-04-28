---
layout: post
title: "Macropad PCB"
date: 2025-10-23
tags: []
---

This project is just a PCB for the macropad build.

- **128×32 display**
- **9 keyboard switches**
- **2 rotary encoders**

It has ESD protection close to screws so its grounded instantly.

{% assign fw = site.pages | where: "path", "projects/electronic/macropad-mldh/index.md" | first %}
{% if fw %}<a class="ref-btn" href="{{ fw.url }}">Whole Project &rarr;</a>{% endif %}

<figure>
  <div class="image-gallery">
    <a href="images/3d_pcb_model.jpg" target="_blank">
      <img src="images/3d_pcb_model.jpg" alt="3D PCB Model">
    </a>

    <a href="images/pcb_layout.jpg" target="_blank">
      <img src="images/pcb_layout.jpg" alt="PCB Layout">
    </a>

    <a href="images/sch.jpg" target="_blank">
      <img src="images/sch.jpg" alt="Schematic">
    </a>
  </div>

  <figcaption>
    Images of schematic and PCB layouts.
  </figcaption>
</figure>
