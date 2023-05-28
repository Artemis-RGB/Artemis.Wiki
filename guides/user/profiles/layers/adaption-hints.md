---
title: Layers - Adaption Hints
description: This guide explains what adaption hints are and how they help sharing profiles.
published: true
date: 2021-05-19T11:41:46.206Z
tags: profiles, layers, adaption hints, exporting, importing
editor: markdown
dateCreated: 2021-05-19T11:41:44.187Z
---

# Introduction
Imagine you've made a great looking profile and you'd like others to enjoy it too. So you go ahead and export it and share it on Discord. **However**, the first person to try it out says: "It looks great, but sadly it doesn't cover the num keys on my keyboard and my fans don't light up at all :(". 

Woops, you never applied the layers to the num keys, because your tenkeyless keyboard doesn't have those. Besides that you don't have any case fans at all, so they aren't included either!

This is where adaption hints come into play. Using these you can tell Artemis what to do with each of your layers when another users imports your profile. This allows you to plan ahead and include all kinds of devices in your profile, even if you don't have them yourself.

# Available hints
Artemis has a few hints available
- **Category adaption hint** - A hint that adapts layers to a certain category of devices.
- **Device adaption hint** - A hint that adapts layers to a certain type of devices.
- **Keyboard section adaption hint** - A hint that adapts layers to a certain region of keyboards.

# Applying hints
Applying hints is done on a per-layer basis (this may be expanded to entire folders in the future).
To do so right-click on a layer inside the editor's **Profile elements** panel and select **<i class="v-icon mdi mdi-auto-fix"></i> View adaption hints**.

In the window that then shows up you can click the **+ button** to start adding hints.
![dialog.png](/guides/user/profiles/adaption-hints/dialog.png){.elevation-3 .radius-5}

Once you've selected a hint you can configure it further, refining how the hint should be acted upon.
![category-hint.png](/guides/user/profiles/adaption-hints/category-hint.png){.elevation-3 .radius-5}

Each hint has a main setting; the category, device type or keyboard section. However the category and device hints also both contain a **Skip** and **Take** option. You can use skip to tell the layer to skip a certain amount of devices and you can use the take option to limit to how many devices the layer is applied. Note that the take option only becomes available when **Take all devices** is unchecked.

> You can add as many hints as you like, so to make a layer apply to multiple categories simply add extra hints.
{.is-info}
