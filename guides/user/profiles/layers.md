---
title: Layers
description: This guide explains what layers are and what they are used for.
published: true
date: 2021-05-19T11:41:47.014Z
tags: 
editor: markdown
dateCreated: 2020-12-22T09:07:24.227Z
---

**Looking for something more specific?**
- [Brushes](/guides/user/profiles/layers/brushes) - This guide explains what brushes are and how they are applied to layers.
- [Effects](/guides/user/profiles/layers/effects) - This guide explains what effects are and how they are applied to layers.
- [Adaption hints](/guides/user/profiles/layers/adaption-hints) - This guide explains what adaption hints are and how they help sharing profiles.

Alternatively, head back to the guide overview on the [getting started](/guides/user) page.

# Introduction
Layers comprise the backbone of Artemis. Every lighting effect in Artemis is caused by a layer of one kind or another. This guide will teach you the basics of the layer system. *This guide is currently a work in progress!*

# Layers and folders
Inside a profile you can create **layers** that display certain effects or colors on a selection of LEDs of your choice. This can be any amount of LEDs, an entire device of even every device in the surface. 

You can organize your layers into **folders**. This is especially helpful when creating large profiles, you can close a folder to hide all the children and keep an overview of your profile structure.

## Brushes
Every layer in Artemis has a **brush**. Brushes specify how a layer should generally behave, but also provide lots of options for you to change how you like. The default brush is the Solid Color brush, which as the name suggests, provides an area (either a rectangle or an ellipse) that is colored a certain color. Properies such as color, scale, width, opacity, and more can be found in the bottom left area of the profile editor (shown below).

![layer-properties.png](/guides/layers/layer-properties.png =400x)

Any of these properties can be manually changed to modify the layer. The General and Transform sections are enabled for every brush, but the properties shown in the brush section depend on the brush. Here we see that the Solid Color Brush has only two properties: the Color Mode, and the Color. You can change the color by manually editing the hex code or clicking the color circle to open the color picker.

## Effects
**Effects** are modifiers than can be applied to any layer. You can add them by clicking the Add Effect button in the bottom right of the Layer Properties section (shown below).

![layer-effects.png](/guides/layers/layer-effects.png =400x)

## Advanced layer usage
Layers can be animated using the [timeline](guides/user/profiles/timeline), you can add [conditions](guides/user/profiles/conditions) to them and you can create [data bindings](guides/user/profiles/data-bindings) to tie their properties to specific data. 

### Timeline

### Conditions

### Data bindings