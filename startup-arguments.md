---
title: Startup arguments
description: A list of startup arguments available to Artemis.UI.exe
published: true
date: 2023-03-03T12:37:38.278Z
tags: arguments, logging, plugin lock, elevation, command line, parameters
editor: markdown
dateCreated: 2021-02-03T09:40:20.734Z
---

 ## How to use
 You may provide one or more startup arguments also known as command line parameters, to Artemis.
 This is done by modifying the shortcut and changing the **Target** value
 ![startup-arguments.png](/startup-arguments.png)

## Available arguments
| Argument                   | Description                                                                                          | Notes                                                                                            |
| -------------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| `--ignore-plugin-lock`     | Ignore artemis.lock files in plugin folders, this means plugins that failed to load are not skipped. | May cause repeaded startup crashes.                                                              |
| `--force-elevation`        | Forces Artemis to run with elevated permissions even when no plugins require it.                     | Has no effect if Artemis is not started as administrator.                                        |
| `--autorun`                | Informs Artemis it is being auto-run.                                                                | Used by the auto-run task, not relevant for users.                                               |
| `--minimized`              | Starts Artemis in the tray, hiding the splash screen and main window.                                | -                                                                                                |
| `--logging={level}`        | Runs Artemis with the specified level of logging.                                                    | Available levels: verbose, debug, information, warning, error, fatal                             |
| `--force-software-render`  | Overrides the preferred render method setting to **software**.                                       | May be used to try and solve crashes on startup.                                                 |
| `--disable-forced-shutdown`| Disables Artemis killing its own process 8 seconds after shutdown                                    | This behaviour is enabled by default to avoid issues with plugins keeping Artemis.UI alive       |
| `--disable-webserver`      | Disables the web server regardless of other settings                                                 | May be used to try and solve crashes on startup.                                                 |
| `--pcmr`                   | Enables 60 FPS and 144 FPS option in settings menu                                                   | Included for fun/testing, almost no device will support this so it's **a waste of performance**. |
| `--channel={channel}`      | Changes the update channel                                                                           | Not recommended unless asked to do so to test something, see [channels](/channels)               |