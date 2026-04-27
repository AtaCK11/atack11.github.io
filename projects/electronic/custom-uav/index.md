---
layout: post
title: "Custom Flight Controller Board"
date: 2026-4-27
tags: [ARM-M33, FlightController, drone]
---

# Project Information

This project is a custom modular FC built around an **ARM Cortex-M33** based **RP2350** microcontroller. Designed to support multiple airframe types including hexacopters, quads and fixed wing drones.
The goal is to eliminate the setup processes of such flight controllers and create a out-of-box experience with minimal setup processes.

- **Built using RPi microprocessors (pico-sdk)**
- **Real-time telemetry system**
- **Modular airframe support with minimal setup** (V1 main focus point)
- **Integrated power distribution board (PDB)** (Least priority)
- **Custom CAN communication bus** (Least priority, will use UART until i finish the FC itself)

## System Architecture

The system is built around modules where each component communicates over a custom protocol. (Unfinished)
This ensures reliable, low-latency and long distance (wired) communications between sensors and control modules.

The integrated PDB simplifies wiring and improves system size to fit in small quadcopers.

## Control Navigation

The firmware focuses heavily on steady, autonomous flying with minimal human interference.

Implemented & Planned features:
- **Mission Planner**
- **Altitude Planner**
- **Auto-Focus camera and locking features.**
- **Basic controls for the pilot like _Stop_, _Return_, _Circle_, _Altitude selector_, _Mission Updater_ etc.**
- **No manual controls of the drone like the FPVs.**

## Telemetry and Communication

The controller provides real-time telemetry over LoRa. And currently uses UART and I2C to communicate between sensors or modules.

Implemented features:
- **Live camera feed over WiFi**
- **Debugging and diagnostics**
- **Expansion with additional modules _(companion computers, payloads, etc.)_**


## Safety and Reliability

Currently bare minimum to fly without taking extras from my wallet.

Implemented & Planned features:
- **Failsafe mechanisms for signal loss** (Implemented)
- **Heartbeat signal** (Implemented)
- **Sensor tests before flight** (Implemented)
- **Power monitoring** (Implemented)
- **Avoiding blacklisted GPS cordinates** (Implemented)
- **Fault detection** (Not implemented)
- **Watchdog system recovery** (Not implemented)
- **Backup processor** (Not implemented)
- **Collision detector** (Not Implemented)

# Blog & Updates

<section class="projects-grid">

{% assign pages_sorted = site.pages | sort: "date" | reverse %}
{% for post in pages_sorted %}
  {% if post.layout == "post" and post.path contains "projects/electronic/custom-uav/" %}
  <a class="project-card uav" data-label="{{ post.date | date: '%Y-%m-%d' }}" href="{{ post.url }}">
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
