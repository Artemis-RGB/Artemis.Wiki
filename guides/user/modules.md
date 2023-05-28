---
title: Transformation Modes
description: An in-depth explanation of the different transformation modes
published: true
date: 2023-04-01T23:58:18.327Z
tags: 
editor: markdown
dateCreated: 2023-04-01T23:58:08.341Z
---

# Introduction
In Artemis a layer can be transformed by using its transformation properties. Depending on the selected transformation mode these properties behave in different ways.

This article will attempt to explain the different modes, the reasoning behind them and give a technical explanation of what's happening.

# The different modes
These will be explained in further detail soon. Here is a quick overview of all of them.
![transformation-modes-overview.png](/profiles/transformation-modes-overview.png)

## Full transform
This is the default transformation mode 

## Clip
This transformation mode only clips (or 'cuts') the brush

## Move
This transformation mode also clips the brush but moves the brush instead of clipping different parts of it

# Reasoning
Having only full transform would be the most obvious choice but then you can't make effects like a bar with a gradient that fills up
Because the gradient would get squeezed together (as seen on the bottom right of the overview)

# Technical explanation
Right now mainly a note to self..

## Full transform
- Brushes fill a scaled and translated path. 
- Rotation is applied afterwards meaning this transformation mode is the only one in with the end result is actually rotated.

## Clip
- Brushes fill a path that is always the full size of the layer.  
- Clipping is applied afterwards using a scaled, translated and rotated path. 
- Rotation affects the clip, not the brush.

## Move
- Brushes fill a path that is always the full size of the layer.  
- Clipping is applied afterwards using a scaled and rotated path
- Rotation affects the clip, not the brush.
- After rendering, translation is applied.

> Maybe move should affect the rotation of the brush.. then the name 'move' no longer discribes it very well though.
{.is-warning}


