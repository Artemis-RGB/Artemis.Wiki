---
title: Introduction to Artemis development
description: An overview of the guides that'll teach you how to develop plugins for Artemis
published: true
date: 2026-01-09T22:05:17.129Z
tags: 
editor: markdown
dateCreated: 2025-10-12T16:20:51.955Z
---

# Introduction
Welcome to the developers section of the Artemis wiki. These articles will serve as a way to help you understand the different types of plugins, the Artemis API and (basic) Artemis internals.

To kind of get an idea of how Artemis is built, these are the technologies we employ.
- ![](/guides/developer/net_core_logo.svg =24x){.mr-2} **.NET 10** - Artemis is written in C# and so .NET is our main framework. Artemis will try to stay up to date with the latest .NET.
- ![](/guides/developer/skia_project_logo.svg =24x){.mr-2} **Skia** - Rendering engine used via SkiaSharp. This is the same engine as the one used in Chrome and Xamarin.
- ![](/guides/developer/rgb-net-icon.png =24x){.mr-2} **RGB.</span>NET** - The RGB library used to create a layer of abstraction between Artemis and the many different RGB devices.
- ![](/guides/developer/avalonia-white-purple.svg =24x){.mr-2} **Avalonia** - A cross platform UI library.
{.grid-list}

# Guides overview
Artemis consists of many different parts but you don't need to know the whole picture before you can start coding. That's why we've split the developer section up into several different guides. 

You can go through these guides in any given order but every section has an introduction that tells you more about the topic you are about to start working on.


## General
These guides tackle general Artemis-related topics such as the Visual Studio templates, the design principles behind Artemis, contributing to the Artemis Core etc.

- [Getting started](/guides/developer/getting-started) - A guide on how to set up a C# project for Artemis development.
- [User interfaces](/guides/developer/user-interfaces) - A guide on how to create custom UI elements for your plugin.

## Plugins
These guides will walk you through each of the plugin types, explain what their use cases are and help you with some general coding guidelines while working on Artemis plugins.

*Work on plugin guides has not yet started.*

- [Brushes](/guides/developer/brushes) - A guide on how to code new brushes.

## Layouts
While not strictly developer territory, each device in Artemis needs a layout to be fully functional. The idea is that whenever someone makes a new layout, we include it in Artemis for others to enjoy.

- [Layouts](/guides/developer/layouts) - This guide will teach you how to create your own layout.