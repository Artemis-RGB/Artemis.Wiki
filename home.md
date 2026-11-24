---
title: The Official Artemis Wiki
description: The perfect place to learn more about Artemis and its usage
published: true
date: 2025-10-13T08:49:52.350Z
tags: 
editor: markdown
dateCreated: 2025-10-12T16:20:38.671Z
---

# Introduction
Welcome to the Artemis 2.x wiki!  
This is the perfect place to learn more about Artemis from a user perspective or as a (plugin) developer.

Right now Artemis 2 is in active development meaning some of the content on this wiki may go out of date and therefore be incorrect. In such a case, feel free to make changes or add new information.

## Downloading Artemis
[![Build Status](https://dev.azure.com/artemis-rgb/Artemis/_apis/build/status/Artemis%20Development%20build?repoName=Artemis-RGB%2FArtemis&branchName=master)](https://dev.azure.com/artemis-rgb/Artemis/_build/latest?definitionId=1&repoName=Artemis-RGB%2FArtemis&branchName=master)
Every time a change is made to Artemis 2, a build is automatically created and uploaded. 

### Windows
The recommended way to install these builds is using the [Artemis installer](https://artemis-rgb.com/binaries/Artemis.Installer.exe). 
- The installer will always install the latest build
- You can use the installer to update Artemis
- You don't need to download the installer to get a new version, just run it again

> You may get a SmartScreen/virus warning but [the installer is virus free](https://www.virustotal.com/gui/url/76024204cec2e930e9420b512d3cb2a2fddd16ed3a25cff06a391edcc1e4d5db/detection) and [so is Artemis](https://www.virustotal.com/gui/url/1528ee6e6ae0ba2f1686a093ff422a309068ada2ef49823535103486e35b7679/detection). 
> This warning is because the installer is not digitally signed (doing so is very expensive).
{.is-warning}

### Linux
There is no graphical installer for Linux. The current recommended way to install Artemis on Linux is with the [install script](https://artemis-rgb.com/binaries/install-artemis-rgb.sh).

The script has been tested in a small amount of Linux installs, so feel free to review it before installing and contact the developers if you have issues or improvements to report.

You can download and execute the script in one go with the following command:
`curl -s -L https://artemis-rgb.com/binaries/install-artemis-rgb.sh | bash`

Alternatively, there are AUR and Flatpak packages available but they are not officially supported by the developers:
Flatpak: https://codeberg.org/Synchro/com.artemis_rgb.Artemis
AUR: https://aur.archlinux.org/packages/artemisrgb-git

Proper Artemis packages for Linux will be revisited once plugins can be downloaded directly from the workshop as this will make it easier to package.

LINUX USERS NOTE: Some effects/brushes in Artemis may not function until/unless you add your user account to the *INPUT* usergroup. This allows Artemis/OpenRGB to read key presses for reactive effects.
### Individual builds
If you don't want to use the installer, you can browse the builds for Windows [here](https://artemis-rgb.com/releases/windows) and Linux [here](https://artemis-rgb.com/releases/linux).  
The installer and the manual downloads both include all plugins from the [Artemis.Plugins repository](https://github.com/Artemis-RGB/Artemis.Plugins)

## Getting started
Check out our [getting started guide](/guides/user) which is a good place to learn more. 
That page contains links to all other guides (also found in the sidebar) and to walkthroughs.

It may also be useful to check out our [FAQ](/faq).

## Providing feedback
Any and all feedback is welcome, but before you do please take a look at the [known issues page](/known-issues).  
The preferred way to report bugs is via the [GitHub issue tracker](https://github.com/Artemis-RGB/Artemis/issues).  
On GitHub you may also post questions and/or ideas but if you prefer you can also do so on our [Discord server](https://discord.gg/S3MVaC9).

## Development
While Artemis 2 is still in development, the plugin API is pretty far along.  
To get started, take a look at our [developer guides](/guides/developer) where we explain how Artemis works on a technical level and walk you through getting started on Artemis plugin development.

## Contributing to the wiki
Any and all help is welcome :) To contribute, [create an account here](https://wiki.artemis-rgb.com/register) (the link is red but it works). 
PS: Please write your pages in Markdown, thank you!