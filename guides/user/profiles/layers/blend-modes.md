---
title: Layers - Blend Modes
description: This guide explains what blend modes are and how layers, folders and profiles mix with what's below them.
published: true
date: 2026-11-24T12:00:00.000Z
tags: profiles, layers, folders, blend modes, effects
editor: markdown
dateCreated: 2026-11-24T12:00:00.000Z
---

**Not what you're looking for?**
Head back to the guide overview on the [getting started](/guides/user) page.

# Introduction
Imagine you've built a great looking rainbow profile, but in the evening you'd like everything to be a bit warmer. So you add an orange layer on top of everything. **However**, instead of a warm rainbow you now have an orange keyboard :(

That's because by default a layer simply draws on top of whatever is below it. Blend modes let you change that. With a blend mode you tell Artemis how the colors of a layer should mix with the colors below it, so that orange layer can tint your rainbow instead of hiding it.

In this guide we'll go over the blend modes of layers, folders and profiles. The images in this guide are made by Artemis itself, with the checkered background showing where nothing is drawn.

# Blend modes on layers
Every layer has a blend mode, you'll find it in the **<i class="v-icon mdi mdi-hammer-wrench"></i> General** category of the layer's properties. The default is **Normal**, which draws the layer on top of what's below it.

When you open the blend mode dropdown you'll see every blend mode with a short description of what it does. They're grouped by what they're good for, like darkening or lightening.

What's "below" a layer is everything that is lower in the **Profile elements** panel, the element at the top of the list is drawn last and ends up on top.

> A blend mode only works inside the area of its layer, everything outside of the layer is left alone.
{.is-info}

# The blend modes
In the examples below the rainbow is below and the orange layer uses the blend mode. Where the orange layer doesn't cover the rainbow, there's nothing to blend with and you'll see what the layer does on its own.

> These examples use a rainbow and a single color to show the differences, but blend modes work with anything a layer draws. Feel free to experiment, it's the quickest way to get a feel for them!
{.is-success}

## Normal
This is the default and what you'll use most of the time.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-src-over.png](/guides/user/profiles/blend-modes/mode-src-over.png =210x) | **Normal** | Draws on top of what's below |

## Darken
These blend modes make what's below darker, which makes them great for tinting or dimming your other layers.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-darken.png](/guides/user/profiles/blend-modes/mode-darken.png =210x) | **Darken** | Keeps the darker of the two colors |
| ![mode-multiply.png](/guides/user/profiles/blend-modes/mode-multiply.png =210x) | **Multiply** | Darkens what's below, white leaves it unchanged |
| ![mode-color-burn.png](/guides/user/profiles/blend-modes/mode-color-burn.png =210x) | **Color burn** | Darkens what's below strongly, white leaves it unchanged |

> Want to make everything a bit dimmer? Use a gray layer with **Multiply**. The darker the gray, the dimmer the result, while a white layer changes nothing at all.
{.is-info}

## Lighten
These blend modes make what's below lighter, they're useful for adding highlights, flashes and other light on top of your effects.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-lighten.png](/guides/user/profiles/blend-modes/mode-lighten.png =210x) | **Lighten** | Keeps the lighter of the two colors |
| ![mode-screen.png](/guides/user/profiles/blend-modes/mode-screen.png =210x) | **Screen** | Lightens what's below, black leaves it unchanged |
| ![mode-color-dodge.png](/guides/user/profiles/blend-modes/mode-color-dodge.png =210x) | **Color dodge** | Lightens what's below strongly, black leaves it unchanged |
| ![mode-plus.png](/guides/user/profiles/blend-modes/mode-plus.png =210x) | **Plus** | Adds the colors together, red and blue make magenta |

## Contrast
These blend modes make the dark parts of what's below darker and the light parts lighter.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-overlay.png](/guides/user/profiles/blend-modes/mode-overlay.png =210x) | **Overlay** | Makes the dark parts of what's below darker and the light parts lighter |
| ![mode-soft-light.png](/guides/user/profiles/blend-modes/mode-soft-light.png =210x) | **Soft light** | A gentler overlay |
| ![mode-hard-light.png](/guides/user/profiles/blend-modes/mode-hard-light.png =210x) | **Hard light** | An overlay driven by this layer's colors instead of what's below |

## Compare
These blend modes compare the two colors, which can give some wild results.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-difference.png](/guides/user/profiles/blend-modes/mode-difference.png =210x) | **Difference** | Subtracts the darker color from the lighter one |
| ![mode-exclusion.png](/guides/user/profiles/blend-modes/mode-exclusion.png =210x) | **Exclusion** | A softer difference |

## Color
These blend modes take part of a color from the layer and the rest from what's below. **Color** is a great one for tinting, everything below takes on the color of the layer but keeps its own brightness.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-hue.png](/guides/user/profiles/blend-modes/mode-hue.png =210x) | **Hue** | Takes the hue of this layer and the rest from what's below |
| ![mode-saturation.png](/guides/user/profiles/blend-modes/mode-saturation.png =210x) | **Saturation** | Takes the saturation of this layer and the rest from what's below |
| ![mode-color.png](/guides/user/profiles/blend-modes/mode-color.png =210x) | **Color** | Takes the hue and saturation of this layer and the brightness of what's below |
| ![mode-luminosity.png](/guides/user/profiles/blend-modes/mode-luminosity.png =210x) | **Luminosity** | Takes the brightness of this layer and the color of what's below |

## Masking
These blend modes don't really mix colors, instead they use the shape of the layer to decide what stays visible. You can use them to cut shapes out of other layers or to only show a layer where something else is lit.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-src-in.png](/guides/user/profiles/blend-modes/mode-src-in.png =210x) | **Src in** | Shows this layer only where something is below, replacing it |
| ![mode-dst-in.png](/guides/user/profiles/blend-modes/mode-dst-in.png =210x) | **Dst in** | Hides this layer, its transparent parts erase what's below |
| ![mode-src-out.png](/guides/user/profiles/blend-modes/mode-src-out.png =210x) | **Src out** | Shows this layer only where nothing is below |
| ![mode-dst-out.png](/guides/user/profiles/blend-modes/mode-dst-out.png =210x) | **Dst out** | Cuts this layer's shape out of what's below |
| ![mode-src-a-top.png](/guides/user/profiles/blend-modes/mode-src-a-top.png =210x) | **Src atop** | Draws on top, but only where something is below |
| ![mode-dst-a-top.png](/guides/user/profiles/blend-modes/mode-dst-a-top.png =210x) | **Dst atop** | Draws behind what's below, its transparent parts erase what's below |
| ![mode-xor.png](/guides/user/profiles/blend-modes/mode-xor.png =210x) | **Xor** | Shows both, except where they overlap |
| ![mode-modulate.png](/guides/user/profiles/blend-modes/mode-modulate.png =210x) | **Modulate** | Like multiply, but only where something is below |

## Other
The last few blend modes are rarely needed, but they're there if you need them.

| Example | Blend mode | What it does |
|---|---|---|
| ![mode-clear.png](/guides/user/profiles/blend-modes/mode-clear.png =210x) | **Clear** | Erases what's below where this layer is |
| ![mode-src.png](/guides/user/profiles/blend-modes/mode-src.png =210x) | **Src** | Replaces what's below, transparent parts included |
| ![mode-dst.png](/guides/user/profiles/blend-modes/mode-dst.png =210x) | **Dst** | Hides this layer and keeps what's below |
| ![mode-dst-over.png](/guides/user/profiles/blend-modes/mode-dst-over.png =210x) | **Dst over** | Draws behind what's below |

# Blend modes on folders
Folders have a blend mode too, you'll find it in the **<i class="v-icon mdi mdi-hammer-wrench"></i> General** category when you select a folder. To understand what it does, it's important to know how Artemis draws a folder.

## Folders blend as a whole
By default Artemis first combines everything inside a folder into one picture and then draws that picture onto what's below the folder. This means the blend modes of the layers inside the folder only mix with the other layers in the same folder.

In the example below the red and green layers are inside a folder and both use **Screen**, the blue layer is below the folder. Where red and green overlap they mix into yellow, but the red layer doesn't mix with the blue one at all because blue is outside of the folder.
![folder-children-screen-normal.png](/guides/user/profiles/blend-modes/folder-children-screen-normal.png =600x){.elevation-3 .radius-5}

The blend mode of the folder itself decides how that combined picture is drawn onto what's below. Below, the red and green layers are back to **Normal** but the folder uses **Screen**. Inside the folder green simply covers red, after which the folder as a whole is screened onto the blue layer.
![folder-screen.png](/guides/user/profiles/blend-modes/folder-screen.png =600x){.elevation-3 .radius-5}

## Pass through
Sometimes you don't want a folder to be combined first. Say you've got a folder full of effects and you want one of them to tint the layers below the folder, or you simply want to keep your tint layer organized in a folder. That's where the **Pass through** blend mode comes in, you'll find it at the top of the folder's blend mode dropdown.

With **Pass through** the folder no longer combines its layers first. Instead each layer inside the folder blends with what's below the folder on its own, as if the folder wasn't there. Here's the first example again, but now with the folder set to **Pass through**. The red layer now mixes with the blue layer below the folder, making magenta.
![folder-children-screen-pass-through.png](/guides/user/profiles/blend-modes/folder-children-screen-pass-through.png =600x){.elevation-3 .radius-5}

> **Pass through** only changes how blending works, everything else about the folder stays the same. Its conditions and timeline still apply to everything inside it.
{.is-info}

## Effects on folders
When you add an effect to a folder, the effect is applied to the folder as a whole. A glow on a folder for example creates a single glow around all of its layers, rather than a separate glow around each layer.
![glow-folder.png](/guides/user/profiles/blend-modes/glow-folder.png =600x){.elevation-3 .radius-5}

This keeps working with **Pass through** for effects that only draw *around* the content of the folder, such as a glow. The glow is drawn around the folder as a whole while the layers inside it still blend with what's below the folder.

Below are two folders with a glow, both containing a red and a blue layer that use **Screen**. The rainbow is below the folder.
- On the left the folder uses **Normal**, red and blue mix with each other but cover the rainbow.
- On the right the folder uses **Pass through**, red and blue also mix with the rainbow, while the glow surrounds the folder just like before.

![glow-folder-screen-normal.png](/guides/user/profiles/blend-modes/glow-folder-screen-normal.png =400x) ![glow-folder-screen-pass-through.png](/guides/user/profiles/blend-modes/glow-folder-screen-pass-through.png =400x)

> Effects that change the content itself, like adjusting its colors, need the folder combined into one picture to work on. If a folder set to **Pass through** contains such an effect, the folder blends as a whole instead, even while the effect is disabled.
{.is-warning}

# Blend modes on profiles
Last but not least, profiles have a blend mode as well. It decides how your profile mixes with the profiles below it. You can change it by hovering over a profile in the sidebar, clicking the <i class="v-icon mdi mdi-cog"></i>-icon and changing the **Blend mode** in the dialog that opens.

Profiles higher up in the sidebar are drawn on top of the profiles below them. This means a profile at the top of your sidebar can tint all of your other profiles, which is exactly what we wanted in the introduction! Below you'll see a profile with a few shapes and a rainbow, with nothing on top.
![profile-below.png](/guides/user/profiles/blend-modes/profile-below.png =600x){.elevation-3 .radius-5}

Now we add a profile above it containing a single amber layer covering everything. With its blend mode set to **Normal** the amber covers everything, just like in the introduction.
![profile-tint-normal.png](/guides/user/profiles/blend-modes/profile-tint-normal.png =600x){.elevation-3 .radius-5}

With the blend mode of the amber profile set to **Multiply** everything below it gets a warm tint, while LEDs that are off stay off.
![profile-tint-multiply.png](/guides/user/profiles/blend-modes/profile-tint-multiply.png =600x){.elevation-3 .radius-5}

With **Color** everything below takes on the amber color while keeping its own brightness.
![profile-tint-color.png](/guides/user/profiles/blend-modes/profile-tint-color.png =600x){.elevation-3 .radius-5}

Profiles are drawn onto LEDs that start out black, that's why these examples have a black background instead of a checkered one. Blend modes that lighten, like **Screen**, will light up LEDs that would otherwise be off.

A profile can use **Pass through** too, then each layer and folder in the profile blends with the profiles below on its own, just like it does in a folder.

> The profile editor only shows the profile you're editing, so you won't see a profile's blend mode in action until you close the editor. The blend mode is also not applied while a profile fades in or out.
{.is-warning}
