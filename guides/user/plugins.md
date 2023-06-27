---
title: Plugins
description: A collection of extra plugins available for Artemis
published: true
date: 2023-06-27T03:24:42.638Z
tags: 
editor: markdown
dateCreated: 2021-08-20T10:19:34.997Z
---

Artemis is built up using plugins. This means devices, brushes, effects and modules (for supporting games!) can all be added via plugins.
On this page you can find a list of extra plugins available to download and use with Artemis.

Under **Settings** > **Plugins** you can find your currently installed plugins, these default plugins are created by Artemis developers.
On that same page you can click **Import plugin**. This is how you install any of the plugins you download below.

## Brushes
Brushes are what you apply to a layer to determine what the layer will display.
Some of the built-in brushes are key press, ambilight, solid, linear gradient, radial gradient etc.

- [<i class="v-icon mdi mdi-animation-play"></i> GIF *Plays a GIF on a layer* *diogotr7*](https://nightly.link/diogotr7/Artemis.Plugins/workflows/dotnet-core/master/Gif)
{.links-list .plugin-list}

## Device providers
Device providers add support for new devices to Artemis. 

- [![](https://raw.githubusercontent.com/Cheerpipe/Artemis.Plugins.Public/master/src/Device/Adalight/Artemis.Plugins.Devices.Adalight/adafruit.svg =20x) Adalight *Allows Artemis to control ARGB Led Strips using an Adalight compatible controller* *Cheerpipe*](https://nightly.link/Cheerpipe/Artemis.Plugins.Public/workflows/plugins/master/Artemis.Plugins.Devices.Adalight)
{.links-list .plugin-list}

## Effects
Effects are what you apply to a layer to change the way the brush is drawn. 
Some of the built-in effects are audio visualization, blur, color adjustment, LED reveal etc.

- [<i class="v-icon mdi mdi-lightbulb-group"></i> Flickering Lights *Provides a game Doom/Half life like light flickering based on common lighting patterns* *Cheerpipe*](https://nightly.link/Cheerpipe/Artemis.Plugins.Public/workflows/plugins/master/Artemis.Plugins.LayerEffect.FlickeringLights)
{.links-list .plugin-list}

## Modules
Modules add extra data to the data model. Some modules are tied to games or applications, others are always available.

- [<i class="v-icon mdi mdi-discord"></i> Discord *Add Discord support with info like mic status, notifications and more* *diogotr7*](/guides/user/plugins/discord)
- [<i class="v-icon mdi mdi-spotify"></i> Spotify *Add Spotify support with playing track information including colors* *diogotr7*](https://nightly.link/diogotr7/Artemis.Plugins/workflows/dotnet-core/master/Spotify)
- [![](https://raw.githubusercontent.com/Cheerpipe/Artemis.Plugins.Public/master/src/Modules/Artemis.Plugins.Modules.FallGuys/FallGuys.svg =20x) Fall Guys *Add support for Mediatonic's Fall Guys game* *Cheerpipe*](https://nightly.link/Cheerpipe/Artemis.Plugins.Public/workflows/plugins/master/Artemis.Plugins.Modules.FallGuys)
- [![](https://raw.githubusercontent.com/AlpacaFur/Artemis.CSGO/main/Artemis.CSGO/csgo-logo.svg =23x) CS:GO *Add support for Counter Strike: Global Offensive* *diogotr7*](https://nightly.link/Artemis-RGB/Artemis.Plugins.Games/workflows/build/master)
- [![](https://raw.githubusercontent.com/AlpacaFur/Artemis.BDDiscord/main/Artemis.BDDiscord/BDDiscord.svg =24x) BetterDiscord *Add support for BetterDiscord (requires client mod)* *AlpacaFur*](https://github.com/AlpacaFur/Artemis.BDDiscord/releases)
- [![](https://github.com/diogotr7/Artemis.Plugins/raw/master/src/Artemis.Plugins.Modules.LeagueOfLegends/LeagueOfLegendsIcon.svg =24x) League Of Legends *Add support for League of Legends* *diogotr7*](https://nightly.link/diogotr7/Artemis.Plugins/workflows/dotnet-core/master/League%20Of%20Legends)
- [![](/vendors/logitech-logo.png =20x) LogiStats *Adds Logitech device data to model (battery, charging status, etc). Updates are pushed from LGHUB (requires Logitech GHUB)* *diogotr7 + th3an7*](https://nightly.link/th3an7/Artemis.Plugins.Modules.LogiStats/workflows/build/master/Artemis.Plugins.Modules.LogiStats)


{.links-list .plugin-list}

## Scripting
Currently there is only the built-in JavaScript scripting provider.

## Wrappers
These plugins provide a wrapper around existing manufacturer's SDKs, allowing you to mirror the output of other applications to a brush which you can apply to all your devices. An example being the Razer integration of Overwatch.

- [<i class="v-icon mdi mdi-alien"></i> LightFX *Mirrors output of LightFX-supported games to a brush* *diogotr7*](https://nightly.link/Artemis-RGB/Artemis.Plugins.Wrappers/workflows/build/master/Artemis.Plugins.Wrappers.LightFx)
- [![](/vendors/logitech-logo.png =20x) Logitech *Mirrors output of Logitech-supported games to a brush* *diogotr7*](https://nightly.link/Artemis-RGB/Artemis.Plugins.Wrappers/workflows/build/master/Artemis.Plugins.Wrappers.Logitech)
- [![](/vendors/razer-logo.png =20x) Razer *Mirrors output of Razer-supported games to a brush* *diogotr7*](https://nightly.link/Artemis-RGB/Artemis.Plugins.Wrappers/workflows/build/master/Artemis.Plugins.Wrappers.Razer)

## Hardware Monitoring
To display sensor data like CPU usage or temperature on your rgb devices, read the [wiki page](https://wiki.artemis-rgb.com/en/guides/user/plugins/hardware-monitoring) 

{.links-list .plugin-list}

## Others
The plugins below extend Artemis in a way that doesn't fall into one of the categories above