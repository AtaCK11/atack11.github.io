---
layout: post
title: "Experimental Macropad Firmware"
date: 2025-10-23
tags: [ARM-M33, keyboard, RP2350]
---

This project is an experimental firmware for my macropad built with **RPi Pico 2** microcontroller.

The firmware enables control for:

- **128x32 display**
- **9 keyboard switches**
- **2 rotary encoders**
- **Configuration light**

It was a challenge to write this firmware as a whole after the PCB was fabricated. I have found that `RP2350-E9` was causing problems with my keyboard's button press code. I pulled it off by hard reseting the GPIO 2 times in a row. I have no idea why it works but it works!

{% assign hw = site.pages | where: "path", "projects/electronic/macropad-mldh/index.md" | first %}
{% if hw %}<a class="ref-btn" href="{{ hw.url }}">Check the whole project &rarr;</a>{% endif %}
<a class="ref-btn" href="https://github.com/AtaCK11/macropad-MLDH" target="_blank">Firmware on GitHub &rarr;</a>

## Command-Line Interface

The firmware is capable of saving the config file to its own flash, so we dont need a seperate app to hold the config for us.
The macropad firmware exposes a simple command-line interface over USB for configuration and testing.  
This makes it possible to adjust key mappings and encoder behavior without reflashing the device.

### Available Commands

- `show`  
  Display the current keymap and encoder assignments.

- `set key <row 0..2> <col 0..2> <macro>`  
  Assign a macro to a key at the specified row and column.

- `set enc <0|1> <cw|ccw> <macro>`  
  Assign a macro to an encoder direction.

- `save`  
  Save the current configuration to non-volatile storage.

- `resetdefaults`  
  Restore the default keymap and encoder configuration.

### Macro Format

Macros can be specified using readable key combinations or raw hexadecimal values.

Supported formats include:

- `ctrl+c`
- `win+shift+s`
- `alt+f4`
- `0xMM:0xKK` - modifier + key
- `0xKK` - key only
