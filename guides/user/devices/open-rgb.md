---
title: OpenRGB
description: A guide explaining what OpenRGB is and how to use it in combination with Artemis
published: true
date: 2021-08-20T10:34:28.917Z
tags: plugin, openrgb, device
editor: markdown
dateCreated: 2020-11-08T09:41:51.395Z
---

# OpenRGB in a nutshell
![openrgb.png](/guides/user/open-rgb/openrgb.png){.align-abstopright}What OpenRGB is, is best explained by its creator **Adam Honse**:
> One of the biggest complaints about RGB is the software ecosystem surrounding it.  Every manufacturer has their own app, their own brand, their own style.  If you want to mix and match devices, you end up with a ton of conflicting, functionally identical apps competing for your background resources.  On top of that, these apps are proprietary and Windows-only.  Some even require online accounts.  What if there was a way to control all of your RGB devices from a single app, on both Windows and Linux, without any nonsense?  That is what OpenRGB sets out to achieve.  One app to rule them all.

*Source: https://gitlab.com/CalcProgrammer1/OpenRGB/-/wikis/home*

## What this means for Artemis
Generally speaking, Artemis relies on manufacturer software to communicate with devices through their SDKs. But in most cases once you replace the manufacturer software with OpenRGB, the SDK will no longer function.  

Luckily OpenRGB offers its own SDK. This means that Artemis can easily talk with OpenRGB which automatically means Artemis inherits support for all devices that work with OpenRGB, even devices that orginally had no SDK!

# Enabling OpenRGB support in Artemis
**Make sure you are using the latest OpenRGB from https://gitlab.com/CalcProgrammer1/OpenRGB/-/releases**

Support for any device/manufacturer is done via [plugins](/guides/user/plugins), the same goes for OpenRGB.  

The OpenRGB plugin is now included with Artemis by default, using it is simple.

1. In OpenRGB, click on the SDK Server tab and click **Start Server** to allow Artemis to talk to OpenRGB
2. When you **restart** Artemis and look under **Settings > Plugins**, you should see the OpenRGB plugin now and any devices detected by the plugin should show up under the **Settings > Devices** tab.

# Supported devices
All devices supporting direct mode in OpenRGB are also supported in Artemis.
For a full list check out https://gitlab.com/CalcProgrammer1/OpenRGB/-/wikis/Supported-Devices
> Devices without direct mode cannot be controlled, this is a hardware limitation.
{.is-danger}
