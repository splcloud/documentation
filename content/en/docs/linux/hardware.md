---
title: Hardware and operating system
linkTitle: Hardware and operating system
weight: 10
description: >-
  Get a Raspberry Pi, choose a memory card, install the operating system and assemble.
---

## Hardware

You can buy the Raspberry Pi from electronics retailers. We have tested:

- Raspberry Pi 4 or 5, Model B (all memory variants)
- for power over the network cable: the official Power-over-Ethernet module (PoE HAT) for the Raspberry Pi 3B+ and 4B

## Memory card

The memory card is the part most likely to fail after many operating hours. SPL Sense writes little, but a high-quality
micro SD card is still worth it. We have had good experiences with "SanDisk Extreme Pro".

Size is hardly an issue: Raspberry Pi OS with desktop fits on 8 GB, and even a lot of measurement data needs barely a
gigabyte. We recommend at least 16 GB.

## Installing the operating system

1. Install the **Raspberry Pi Imager** on your computer (available on the Raspberry Pi website).
2. Use it to write **Raspberry Pi OS with Desktop** to the memory card.
   - Choose 32 or 64 bit. For a Raspberry Pi 5 we recommend 64 bit. Remember your choice: you need the matching package
     when installing SPL Sense.
   - In the Imager settings, set a user name and password, and switch on **SSH** if you want to set up the Raspberry Pi
     from another computer.

If you are experienced with the command line and don't need a screen on the Raspberry Pi, **Raspberry Pi OS Lite**
without desktop is enough. This guide assumes the desktop variant.

## Assembling

1. Install the Raspberry Pi with the desired add-on modules in the case and insert the memory card.
2. Connect screen, keyboard and mouse.
3. Connect power (or the network cable with PoE). The Raspberry Pi starts.
4. On first start, set up a network connection, by cable or Wi-Fi. SPL Sense is downloaded from the internet in the
   next step.
5. If not already switched on in the Imager: enable SSH under Raspberry menu › **Preferences** ›
   **Raspberry Pi Configuration** › **Interfaces**.
6. Note the IP address of the Raspberry Pi: it appears when you hover the mouse over the network icon at the top right.
