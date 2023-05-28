---
title: JetBrains Proflling Guide
description: A guide explaining how to use the profiling plugin to debug memory/CPU usage problems
published: true
date: 2021-11-21T19:09:20.323Z
tags: 
editor: markdown
dateCreated: 2021-11-06T11:55:05.381Z
---

# JetBrains Profiling
If you are running into issues with high CPU or memory usage in Artemis, we may ask you to take a (few) profile samples.
On this page you can find a step-by-step explanation of how to do this.

## CPU profiling
To profile high CPU usage we use the **CPU Profiler** feature of the **JetBrains Profiling** plugin that is installed by default.

1. Head into Settings > Plugins and search for the **JetBrains Profiling** plugin
2. Enable the **CPU Profiler** feature, letting Artemis install the prerequisites.
3. Click on the plugin's **SETTINGS** button to open the profiling interface.
4. Under Profile CPU usage click on **START** and choose a directory in which to save the snapshots.
5. Wait for profiling to start.
6. Take multiple snapshots when CPU usage is high or click on **SNAPSHOT & STOP** after a few seconds if CPU usage is at a constant high.
7. Uploading the resulting snapshot somewhere, per example https://wetransfer.com/

## Memory profiling
To profile high memory usage we use the **Memory Profiler** feature of the **JetBrains Profiling** plugin that is installed by default.

1. Head into Settings > Plugins and search for the **JetBrains Profiling** plugin
2. Enable the **Memory Profiler** feature, letting Artemis install the prerequisites.
3. Click on the plugin's **SETTINGS** button to open the profiling interface.
4. Under Profile memory usage usage click on **START** and choose a directory in which to save the snapshots.
5. Wait for profiling to start.
6. Take multiple snapshots when memory usage is high or click on **SNAPSHOT & STOP** after a few seconds if memory usage is at a constant high.
7. Uploading the resulting snapshot somewhere, per example https://wetransfer.com/

> When you finish profiling you can optionally choose to remove the profilers again, they take up about ~100mb each.  
You can do this by clicking on the three dots behind the plugin feature and selecting **Remove Prerequisites**.
{.is-info}
