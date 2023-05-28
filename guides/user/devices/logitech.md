---
title: Logitech
description: An overview of the Logitech support provided by the default Artemis Logitech plugin
published: true
date: 2023-03-05T09:20:35.484Z
tags: 
editor: markdown
dateCreated: 2021-03-14T09:26:59.032Z
---

# Introduction
![logitech-logo.png](/vendors/logitech-logo.png){.align-abstopright}Artemis supports Logitech RGB products through the official LED Illumination SDK.

# Requirements
For Logitech support you need to have the latest version of [G Hub](https://www.logitechg.com/en-us/innovation/g-hub.html) or [Logitech Gaming Software](https://support.logi.com/hc/en-us/articles/360025298053-Logitech-Gaming-Software) (LGS) installed and running.
You also need one or more G Hub-enabled Logitech devices.

- The plugin commmunicates with G Hub/LGS, make sure it is running in the background.
- Ensure G Hub/LGS is up-to-date.
- Ensure the SDK is enabled.

# Troubleshooting
Altough Logitech support is tested to be working, everyone's setup is different. Below you can find things to try to solve common errors.

## Plugin not working
First make sure you meet all the requirements stated above. Your software may be out-of-date or the SDK may be disabled for some reason.

If you're still having issues try reinstalling G Hub/LGS, whichever you use. Make sure you **reboot** inbetween so follow these steps:

1. Shut down Artemis if it is running
2. Uninstall your respective Logitech software
3. **Reboot**
4. Reinstall your software
5. **Reboot**
6. Run Artemis

# Supported devices
Artemis can support any device supported by the Logitech Illumination SDK but in order to identify which device is which, we need a `PID` which is an ID unique to Logitech products.

| Device                                       | Type     | Lighting type | Has layout |
|----------------------------------------------|----------|---------------|------------|
| Logitech G910                                | Keyboard | Per key       | Yes        |
| Logitech G910v2                              | Keyboard | Per key       | Yes        |
| Logitech G815                                | Keyboard | Per key       | Yes         |
| Logitech G915                                | Keyboard | Per key       | Yes         |
| Logitech G915 TKL                            | Keyboard | Per key       | Yes         |
| Logitech G810                                | Keyboard | Per key       | Yes        |
| Logitech G610                                | Keyboard | Per key       | Yes        |
| Logitech G512                                | Keyboard | Per key       | No         |
| Logitech G512 SE                             | Keyboard | Per key       | No         |
| Logitech G410                                | Keyboard | Per key       | No         |
| Logitech G213                                | Keyboard | Per key       | No         |
| Logitech G Pro Keyboard                      | Keyboard | Per key       | No         |
| Logitech G19                                 | Keyboard | Per device    | No         |
| Logitech G19s                                | Keyboard | Per device    | No         |
| Logitech G600                                | Mouse    | Per device    | No         |
| Logitech G300s                               | Mouse    | Per device    | No         |
| Logitech G510                                | Keyboard | Per device    | No         |
| Logitech G510s                               | Keyboard | Per device    | No         |
| Logitech G13                                 | Keypad   | Per device    | No         |
| Logitech G110                                | Keyboard | Per device    | No         |
| Logitech G710+                               | Keyboard | Per device    | No         |
| Logitech G105                                | Keyboard | Per device    | No         |
| Logitech G15                                 | Keyboard | Per device    | No         |
| Logitech G11                                 | Keyboard | Per device    | No         |
| Logitech G213                                | Keyboard | 5 zones       | No         |
| Logitech G903                                | Mouse    | 2 zones       | Yes         |
| Logitech G900                                | Mouse    | 2 zones       | Yes         |
| Logitech G703                                | Mouse    | 2 zones       | Yes         |
| Logitech G502 HERO                           | Mouse    | 2 zones       | Yes         |
| Logitech G502                                | Mouse    | 2 zones       | Yes         |
| Logitech G403                                | Mouse    | 2 zones       | Yes         |
| Logitech G303                                | Mouse    | 2 zones       | No         |
| Logitech G203                                | Mouse    | 1 zone        | Yes         |
| Logitech G Pro                               | Mouse    | 1 zone        | Yes         |
| Logitech G Pro Wireless                      | Mouse    | 1 zone        | Yes         |
| Logitech G Pro Hero                          | Mouse    | 1 zone        | Yes         |
| Logitech G633                                | Headset  | 2 zones       | No         |
| Logitech G933                                | Headset  | 2 zones       | No         |
| Logitech G935                                | Headset  | 2 zones       | No         |
| Logitech G560                                | Speaker  | 4 zones       | No         |
