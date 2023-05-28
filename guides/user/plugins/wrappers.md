---
title: Wrapper Plugins Guide
description: Instructions on how to use Wrapper plugins for game integrations
published: true
date: 2022-03-22T07:55:24.445Z
tags: 
editor: markdown
dateCreated: 2022-01-25T00:46:56.223Z
---

# Wrapper Plugins
Note: Please read the [guide](/en/guides/user/plugins/universal-native-integrations) first.

[Repository Link](https://github.com/Artemis-RGB/Artemis.Plugins.Wrappers)

Currently there are three wrapper plugins available, will each working slightly differently:

### Logitech Lightsync

[Supported Games](https://www.pcgamingwiki.com/wiki/RGB_lighting_middleware#Logitech_G_Lightsync)

To keep compatibility for both Logitech Gaming Software and Logitech G HUB, the Lightsync API dynamically loads a dll based on a registry key. We abuse this by writing to that registry key, making the Lightsync API load our custom dll instead of the official Logitech one. The dll then writes data to Artemis automatically.

No additional setup is needed once the Artemis plugin is loaded and its prerequisites automatically install.

### Dell LightFX

[Supported Games](https://www.pcgamingwiki.com/wiki/RGB_lighting_middleware#Alienware_AlienFX)

The LightFX API is loaded by the game without any known verification. This makes the dll trivial to place - either in the game exe folder or in the Windows system32 folder.

The plugin should place both the 32-bit and 64-bit dll in the appropriate system directories.

### Razer Chroma
[Supported Games](https://www.pcgamingwiki.com/wiki/RGB_lighting_middleware#Razer_Chroma_RGB)
