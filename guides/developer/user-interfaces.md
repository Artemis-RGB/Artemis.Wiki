---
title: User Interfaces for plugins
description: A guide on how to create UI elements in plugins
published: true
date: 2026-01-09T22:03:33.476Z
tags: 
editor: markdown
dateCreated: 2026-01-09T22:03:31.944Z
---

# Introduction
It is possible for plugins to define some UI elements in a few places inside Artemis. These can allow users to configure plugins and interact with the features it offers.

### Some common use cases

- A configuration window for the entire plugin
- Advanced config for a layer brush or effect
- Visual scripting nodes that requires more than simple pins

Artemis uses a UI framework called [Avalonia](https://avaloniaui.net/) and you can utilise this in plugins too to create UIs.

# Introduction to Avalonia in Artemis
TODO, explain we use MVVM and that you should be aware of INotifyPropertyChanged 