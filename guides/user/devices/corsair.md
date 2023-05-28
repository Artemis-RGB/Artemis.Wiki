---
title: Corsair
description: An overview of the Corsair support provided by the default Artemis Corsair plugin
published: true
date: 2022-08-07T11:23:56.609Z
tags: corsair
editor: markdown
dateCreated: 2021-03-02T10:00:49.566Z
---

# Introduction
![corsair-logo.png](/vendors/corsair-logo.png){.align-abstopright}Artemis supports Corsair RGB products through the official iCUE SDK.

# Requirements
For Corsair support you need to have the latest version of [iCUE](https://www.corsair.com/eu/en/downloads) installed and running.
You also need one or more iCUE-enabled Corsair devices.

- The plugin commmunicates with iCUE, make sure it is running in the background.
- Ensure iCUE is up-to-date - To check open iCUE go to **Settings** > click **Check for update** in the bottom.
- Ensure the SDK is enabled  - To check open iCUE go to **Settings** > make sure **Enable SDK** is checked.

# Troubleshooting
Altough Corsair support is thourougly tested, everyone's setup is different. Below you can find things to try to solve common errors.

## Plugin not working
First make sure you meet all the requirements stated above. Your iCUE may be out-of-date or the SDK may be disabled for some reason.

If the plugin didn't work you likely got one of the following errors:
**ServerNotFound**
iCUE is not running or was shut down or SDK is disabled in iCUE settings.
**NoControl**
If some other client has or took over exclusive control.
**IncompatibleProtocol**
Either your iCUE is too old or too new, if you're running the latest iCUE please contact us on Discord or GitHub.

## Devices hooked up to a Commander (Pro) are being shuffled after each reboot
This is related to how you have your Commander connected to your motherboard, ensure you plug it directly into one of the USB headers on your motherboard.

## Plugin enables but reports no devices
This can be caused by a corrupt iCUE installation. You can try a clean install of iCUE using Corsair's guide: https://help.corsair.com/hc/en-us/articles/360025166712-Perform-a-clean-reinstallation-of-the-Corsair-Utility-Engine-iCUE-

# Supported devices
Artemis supports all Corsair devices supported by iCUE.

> TODO: Create a table of all devices so we can keep track of which ones are missing a layout
{.is-info}
