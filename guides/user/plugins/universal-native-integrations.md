---
title: Guide - Using native game integrations on all devices
description: Guide on how to get Razer Chroma, Logitech Lightsync, Alienware LightFx, etc. on other devices. 
published: true
date: 2022-01-25T00:46:58.842Z
tags: 
editor: markdown
dateCreated: 2022-01-24T21:54:32.791Z
---

# Guide - Using native game integrations on all devices
## Introduction

Hardware manufacturers provide illumination SDKs used by game developers to enrich the gaming experience. Some examples of this are:
* [Apex Legends](https://www.youtube.com/watch?v=ffvneEPgPqk)
* [Battefield 1](https://www.youtube.com/watch?v=lJEar6RCis8)
* Overwatch
* The Division

Depending on the game and the integration it uses, it's possible to redirect these effects so that instead of the original software receiving them (Razer Synapse, Logitech G HUB, etc.), Artemis receives them instead. This means it's possible to get the native integration for these games on any Artemis-supported hardware, including hardware the games do not support originally.

## Methods of getting illumination data

For Artemis to acquire this data, it needs to access either the game or the original manufacturer software. 

### Wrappers

These work by replacing the original dll that handles these effects, either globally in the system directory, or on a per-game basis by placing the dll in the game directory. These "wrapper" dlls will receive the illumination data sent from the game, and will send that data to Artemis (as long as the required plugin is installed and loaded).

The advantage of this method is it removes the need for additional software. That is, no other software apart from the game and Artemis need to be running for it to work.

The disadvantage is that most recent games (especially competitive ones) check the integrity of the illumination dll before loading it. Our dll is of course not approved by the game developers, which means it either will not be loaded, or wil be flagged as a cheat. Some older competitive games will still load these wrapper Dlls (Battlefield 1 for example).
[Click Here for more info](/guides/user/plugins/wrappers)

### Chroma Grabber

For Razer Chroma integrations explicitly, *most* games block unverified dlls. Because of this, the chroma wrapper is not very useful. It's instead recommended to use the Chroma Grabber plugin, since that method does not require any unverified dll's from being loaded by games.
[Click Here for more info](/guides/user/plugins/chroma)
