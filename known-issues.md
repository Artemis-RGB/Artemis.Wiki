---
title: Known issues
description: Problems, bugs and missing features we are aware off
published: true
date: 2021-09-24T19:20:26.226Z
tags: 
editor: markdown
dateCreated: 2020-12-22T09:32:21.958Z
---

# Introduction
On this page we'll try to keep an up-to-date record of things that are know to be broken, missing or not easy to use.

Before you report an issue please check out this list but also [take a look at GitHub](https://github.com/Artemis-RGB/Artemis/issues) to see if your issue is already described there. This page is mainly for larger scale issues.

## General


## Layouts
- Having LEDs smaller than 5mm will cause issues at a render scale lower than 100%. Until a proper fix is found, try making sure your LEDs are never smaller than 10mm.
- Overlapping LEDs bleed colors

## Device providers
Device provider issues are generally related to problems with the SDK. Sadly we do not always have a way to fix these issues.

### ASUS
- The ASUS device provider may cause random crashes. Artemis will shut down without showing any error message. If you have an ASUS keyboard please contact us on Discord. 

### Logitech
- PowerPlay devices cannot be controlled via the official Logitech SDK, you can instead use [OpenRGB](/guides/user/devices/open-rgb).