---
title: Hardware Monitoring
description: Ways of using hardware monitoring data to create effects
published: true
date: 2023-05-27T21:24:06.413Z
tags: 
editor: markdown
dateCreated: 2023-05-27T21:23:55.079Z
---

# Hardware Monitoring
Artemis has several ways of gathering monitoring data from CPUs, GPUs, RAM, etc. like usage, temperature, clock speed etc.
This means you can make your GPU turn a different color when its core temperature is above 70 degrees, for example.

There are several plugins capable of this, depending on how much information is needed and what additional programs might be running.
# Available options

## Default Performance plugin
This plugin comes bundled with Artemis and works out of the box. Unfortunately, it only supports a limited amount of hardware and only provides a limited amount of information:
- CPU Usage
- Ram Usage

## HWiNFO64 - Recommended

This is generally the best option, as it provides the most information and is the most efficient. It is also the easiest to set up.

### Installation
1. Download and install [HWiNFO64](https://www.hwinfo.com/download/)
2. Run HWiNFO64 in the background
3. Make sure the `Shared Memory Support` option is enabled in HWiNFO64 (Options -> Shared Memory)
4. Download the [HWiNFO64 plugin](https://nightly.link/Artemis-RGB/Artemis.Plugins.HardwareMonitors/workflows/build/master/Aida64.zip)
5. Import the plugin into Artemis (Plugins -> Import Plugin)

### Usage
The plugin will automatically detect the running HWiNFO64 instance and start reading data from it.
To use the data, you can use the provided Module. Please refer to the documentation for profiles for more information on how to use data from Modules.

### Notes
- The plugin will only work if HWiNFO64 is running in the background.
- Since version x, HWiNFO64 has a 12 hour time limit for shared memory support. This means that the plugin will stop working after 12 hours. Restarting HWiNFO64 will reset the timer. The paid version of HWiNFO64 does not have this limitation.

Like the WMI version of OpenHardwareMonitor, this plugin depends on HWiNFO64 running in the background. As such, admin privileges are not required.
It uses shared memory to communicate with HWiNFO64, so it is faster and more efficient than the OpenHardwareMonitor (WMI) plugin.

## Open Hardware Monitor (WMI)

This plugin uses the WMI interface of OpenHardwareMonitor to read data from the hardware. This means that it is slower and less efficient than the HWiNFO64 plugin, but it might support more hardware.

### Installation
1. Download and install [OpenHardwareMonitor](https://openhardwaremonitor.org/downloads/) or [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor/releases)
2. Run OpenHardwareMonitor/LibreHardwareMonitor in the background
3. Download the [OpenHardwareMonitor plugin](https://nightly.link/Artemis-RGB/Artemis.Plugins.HardwareMonitors/workflows/build/master/OpenHardwareMonitor.zip)
4. Import the plugin into Artemis (Plugins -> Import Plugin)

### Usage
The plugin will automatically detect the running OpenHardwareMonitor/LibreHardwareMonitor instance and start reading data from it.
To use the data, you can use the provided Module. Please refer to the documentation for profiles for more information on how to use data from Modules.

## Open Hardware Monitor (Standalone)

This plugin uses the standalone version of OpenHardwareMonitor to read data from the hardware. This means you don't need to install OpenHardwareMonitor, but Artemis will need admin privileges.

### Installation
1. Download the [OpenHardwareMonitor plugin](https://nightly.link/Artemis-RGB/Artemis.Plugins.HardwareMonitors/workflows/build/master/Standalone.zip)
2. Import the plugin into Artemis (Plugins -> Import Plugin)
3. Artemis will restart itself to request admin privileges. This is required to read from the hardware.

### Usage
The plugin will automatically start reading data from the hardware.
To use the data, you can use the provided Module. Please refer to the documentation for profiles for more information on how to use data from Modules.

## AIDA64

This is the least recommended option, as it is the least efficient and requires a paid program. The data it provides is also more limited.

### Installation
1. Download and install [AIDA64](https://www.aida64.com/downloads)
2. Run AIDA64 in the background
3. Make sure the `External Applications` option is enabled in AIDA64 (Preferences -> Hardware Monitoring -> External Applications)
4. Download the [AIDA64 plugin](https://nightly.link/Artemis-RGB/Artemis.Plugins.HardwareMonitors/workflows/build/master/Aida64.zip)
5. Import the plugin into Artemis (Plugins -> Import Plugin)

### Usage
The plugin will automatically detect the running AIDA64 instance and start reading data from it.
To use the data, you can use the provided Module. Please refer to the documentation for profiles for more information on how to use data from Modules.

# Source code
https://github.com/Artemis-RGB/Artemis.Plugins.HardwareMonitors