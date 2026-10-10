---
title: "Waveshare ESP32-S3-Touch-LCD-4 Home Assistant Setup"
description:
  EspControl on the Waveshare ESP32-S3-Touch-LCD-4 V4.0 — a 4-inch round 480×480 touchscreen with 9 cards.
---

# Waveshare ESP32-S3-Touch-LCD-4

The **Waveshare ESP32-S3-Touch-LCD-4 V4.0** is a 4-inch round touchscreen panel with a 480×480 RGB display, GT911 capacitive touch, and ESP32-S3 processor. EspControl provides a 3×3 grid with **9 cards** and two shared image-card slots.

This configuration targets the **V4.0 board revision**, which uses a CH32V003 helper controller for the display reset and backlight. Earlier revisions use different hardware; do not install this package on them.

## Card Grid

<!--@include: ../generated/screens/waveshare-esp32-s3-touch-lcd-4-grid.md-->

The panel's active display area is round, although its graphics resolution is 480×480. The screen layout uses the same compact 3×3 profile as other 480×480 ESP32-S3 panels.

## Install

Connect the display to your computer with a USB-C data cable, then select the Waveshare ESP32-S3-Touch-LCD-4 in the installer.

<!--@include: ../generated/screens/waveshare-esp32-s3-touch-lcd-4-install.md-->

For WiFi setup and Home Assistant pairing, see the [Install guide](/getting-started/install).

## ESPHome Manual Setup

To compile the firmware yourself, select the V4.0 package:

```yaml
substitutions:
  name: "espcontrol-kitchen"
  friendly_name: "EspControl Kitchen"

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

packages:
  api_encryption:
    url: https://github.com/jtenniswood/espcontrol/
    file: common/addon/api_encryption_dynamic.yaml
    refresh: 1sec
  setup:
    url: https://github.com/jtenniswood/espcontrol/
    file: devices/waveshare-esp32-s3-touch-lcd-4/packages.yaml
    refresh: 1sec
```

See the [manual ESPHome setup guide](/getting-started/manual-esphome-setup) for the complete process.
