---
title: Introduction to Artemis development
description: An overview of the guides that'll teach you how to develop plugins for Artemis
published: true
date: 2020-12-22T09:33:56.544Z
tags: 
editor: markdown
dateCreated: 2020-12-01T14:55:10.385Z
---

# Introduction
Welcome to the developers section of the Artemis wiki. These articles will serve as a way to help you understand the different types of plugins, the Artemis API and (basic) Artemis internals.

To kind of get an idea of how Artemis is built, these are the technologies we employ.
- ![](/guides/developer/net_core_logo.svg =24x){.mr-2} **.NET Core 5** - Artemis is written in C# and so .NET Core is our main framework. Artemis will try to stay up to date with the latest .NET Core.
- ![](/guides/developer/skia_project_logo.svg =24x){.mr-2} **Skia** - Rendering engine used via SkiaSharp. This is the same engine as the one used in Chrome and Xamarin.
- ![](/guides/developer/rgb-net-icon.png =24x){.mr-2} **RGB.</span>NET** - The RGB library used to create a layer of abstraction between Artemis and the many different RGB devices.
- ![](/guides/developer/md4xaml.png =24x){.mr-2} **Material Design In XAML** - UI library used in combination with WPF to create the Material-themed UI.
{.grid-list}

# Guides overview
Artemis consists of many different parts but you don't need to know the whole picture before you can start coding. That's why we've split the developer section up into several different guides. 

You can go through these guides in any given order but every section has an introduction that tells you more about the topic you are about to start working on.


## General
These guides tackle general Artemis-related topics such as the Visual Studio templates, the design principles behind Artemis, contributing to the Artemis Core etc.

*Work on general guides has not yet started.*

## Plugins
These guides will walk you through each of the plugin types, explain what their use cases are and help you with some general coding guidelines while working on Artemis plugins.

*Work on plugin guides has not yet started.*

## Layouts
While not strictly developer territory, each device in Artemis needs a layout to be fully functional. The idea is that whenever someone makes a new layout, we include it in Artemis for others to enjoy.

- [Layouts](/guides/developer/layouts) - This guide will teach you how to create your own layout.