---
title: Frequently Asked Questions
description: A good place to find answers to some of the most common questions
published: true
date: 2023-03-15T20:46:33.906Z
tags: 
editor: markdown
dateCreated: 2020-11-04T14:55:01.766Z
---

On this page we'll try to answer some of the most frequently asked questions. If your question is not answered here or you'd like further elaboration, feel free to reach out to us on [Discord](https://discord.gg/S3MVaC9).

# General
## Q: What is the release window for Artemis 2?
**A:** Right now it's hard to say. You can already use Artemis 2 if all you want are simple brushes and animations without any game interaction.  

However, the plan is to create some kind of beta release with things like a proper installer and auto-update before work on the workshop starts, early 2021.

## Q: Who creates Artemis 2?
**A:** The core systems, UI and default plugins are developed by [Robert](https://github.com/RobertBeekman) and I'm also writing this page!  
Aside from that Artemis relies heavily on [RGB.NET](https://github.com/DarthAffe/RGB.NET) by [DarthAffe](https://github.com/DarthAffe), who also has done some work on Artemis and provided a lot of behind the scenes feedback. 

Many people have helped out over the past few months with feedback and pull requests. An honorable mention being [DrMeteor](https://github.com/diogotr7) who has been a very early adopter of the plugin API and Artemis in general.

A big thanks to everyone that has helped out! <3

## Q: Is Artemis cross-platform?
**A:** Yes. Artemis can run on Windows, Linux and MacOS (untested). Do note that on anything but Windows you'll mostly be limited to the OpenRGB plugin because most SDKs won't work there.

## Q: In [Aurora](https://www.project-aurora.com/) I can do {something} and {something}, can Artemis do it too?
**A:** While Artemis and Aurora attempt to solve similar problems, they both do it in *very* different ways. Many people coming from Aurora may try to use Artemis as if its a new version of Aurora which raises a lot of questions that don't apply to Artemis.

All I can say is, go through the Artemis guides and if at the end of that there's still a feature you're missing, let us know and perhaps we can improve upon that :)

# Devices
## Q: Can you add support for my keyboard/mouse/lawn mower?
**A:** All device support in Artemis is done via plugins. This means that in order to add support for a new device, a plugin has to be updated or created. Right now we do not take requests for plugins but the workshop will feature a request system.

If your device is of a brand already supported by the default Artemis plugins but it does not show up, please create a GitHub issue on the [Artemis.Plugins repository](https://github.com/Artemis-RGB/Artemis.Plugins/issues).

> If you want to add support yourself by creating a plugin, check out the [developer guides](/guides/developer).
{.is-info}

## Q: My device is missing an image and the LEDs are in the wrong place, what's wrong?
**A:** This means your device has no layout. For each device we need to create a layout to tell Artemis where the LEDs are precisely. The layout can also contain a device image which Artemis uses in the editor. 

> You can help with this, even if you're not a programmer! Everything is explained in our [layout guide](/guides/layouts).
{.is-info}

# Games
## Q: Can you add support for my favorite game?
**A:** Just like with devices, support for games is done via plugins. Again, the workshop will be the best source for plugins and right now the focus is on getting the Artemis core systems ready.

## Q: What kind of games will likely be supported?
**A:** We hope to provide many easy tools for creating game plugins but in general the more moddable a game is, the easier it will be to create a plugin. Multiplayer games will be harder to support because many ways of reading game data can also be abused by cheats.