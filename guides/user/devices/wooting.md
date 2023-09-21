---
title: Wooting
description: An overview of the Wooting support provided by the default Artemis Wooting plugin
published: true
date: 2023-09-21T00:44:32.459Z
tags: 
editor: markdown
dateCreated: 2023-04-14T12:38:33.607Z
---

# Introduction
![wooting-logo.png](/vendors/wooting-logo.png){.align-abstopright}Artemis supports Wooting RGB keyboards through the official Wooting SDKs.

# Requirements
Assuming you have a supported Wooting keyboard; the Wooting Device Provider, Wooting Profile Module and Wooting Layer Brush Provider
features of the Wooting Device Plugin should work out of the box.

In order to use the Wooting Analog Module, you'll need to install the Wooting Analog SDK.

## Windows

On Windows the SDK & Wooting Plugin will be installed & updated automatically through Wootility (>= v3.4). 

If you wish to install manually, download the latest `.msi` from the [latest release](https://github.com/WootingKb/wooting-analog-sdk/releases)

After installing, restart Artemis and the Analog Module should now work.
<br>
## Linux

On Debian-based distros of Linux, Wooting provides a `deb` package which is an easy to install method of getting the Wooting SDK and Pl
ugin installed.
However if you aren't running a Debian-based distro, don't fret! It's not too difficult to get things working for your distro.

#### Debian-based (Debian, Ubuntu, Pop! OS, etc.)
- You can simply install the `deb` package, which includes both the SDK and the Wooting Plugin, which can be found on the [latest release page](https://github.com/WootingKb/wooting-analog-sdk/releases).
- Restart Artemis and the Analog Module should now work.

[Here is some helpful information](https://linuxhint.com/install_deb_packages_ubuntu/) for installing a `deb` package manually. For all (terminal instructions) and Ubuntu (GUI instructions)
<br>
#### Manual (Fedora, Arch, etc.)
- Download and extract the [latest release](https://github.com/WootingKb/wooting-analog-sdk/releases) `unknown-linux-gnu.tar.gz` archive.
- Copy `<extracted folder>/wrapper/sdk/libwooting_analog_sdk.so` to `/usr/lib`. (Or to some directory and add that path to the `LD_LIBRARY_PATH` environment variable)
- Copy `<extracted folder>/wrapper/sdk/libwooting_analog_sdk.so` to `/usr/lib`.
- Copy `<extracted folder>/wrapper/sdk/libwooting_analog_plugin.so` to `/usr/local/share/WootingAnalogPlugins/wooting-analog-plugin`.
- If the destination folder for the Wooting Analog Plugin does not exist, you can run the following:
	`mkdir -p /usr/local/share/WootingAnalogPlugins/wooting-analog-plugin`
  
Restart Artemis and the Analog Module should now work.
<br>
## macOS
As of writing, note that macOS builds of Artemis are untested and may not work correctly.
#### Homebrew (Recommended)
- Install Homebrew from [their website](https://brew.sh/)
- Open the terminal and enter the command below:
	`brew install wootingkb/wooting/wooting-analog-sdk`

Restart Artemis and the Analog Module should now work.
<br>
#### Manual
- Download and extract the [latest release](https://github.com/WootingKb/wooting-analog-sdk/releases) `apple-darwin.tar.gz` archive.
- Copy `<extracted folder>/wrapper/sdk/libwooting_analog_sdk.dylib` to `/usr/local/lib`. (Or to some directory and add that path to the `DYLD_LIBRARY_PATH` environment variable)
- Additionally, you may need to adjust security settings for macOS to let it run. See the following [Apple Support Article (HT202491)](https://support.apple.com/en-ca/HT202491).
- Copy `<extracted folder>/wrapper/sdk/libwooting_analog_plugin.so` to `/usr/local/share/WootingAnalogPlugins/wooting-analog-plugin`.
- If the destination folder for the Wooting Analog Plugin does not exist, you can run the following:
	`mkdir -p /usr/local/share/WootingAnalogPlugins/wooting-analog-plugin`

Restart Artemis and the Analog Module should now work.
<br>
# Troubleshooting
## Plugin is not working
![screenshot_20230920_194043.png](/screenshot_20230920_194043.png)
See [Requirements](#Requirements) above to install the Wooting Analog SDK on your Operating System.

## I'm using a Linux distro that runs SELinux (like Fedora) and after manually installing the Analog SDK the Analog Module still doesn't work
As the files that you manually installed haven't been labeled by SELinux, it will block them from being used.

To fix this you'll need to auto-relabel your system. 
This sounds scary but is really a single command (and a reboot) away.
- Run `sudo touch /.autorelabel` in a terminal
- Reboot your system, it might take a few seconds/minutes for the process to be complete. 

After this the Wooting Analog Module should work.
<br>
# Supported devices
All Wooting Devices running the V2 firmware should work out of the box.
