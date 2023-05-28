---
title: Conditions
description: This guide explains what conditions are and what kind of conditions you can define to create layers that respond to conditions and events.
published: true
date: 2023-02-12T16:36:45.321Z
tags: 
editor: markdown
dateCreated: 2020-12-22T09:09:05.456Z
---

**Not what you're looking for?**
Head back to the guide overview on the [getting started](/guides/user) page.

# Introduction
In Artemis you can use conditions to make profiles, folders and layers show or hide when certain criteria are met. 

Conditions usually rely on the **data model**. This is the place where Artemis stores all the information available to profiles. There is a **global data model** which is always available *(per example: system metrics, current time, active window)* and a **module-specific data model** which contains data limited to the module the profile is bound to *(per example: health, ammo, team in the current game)*.

**Per example:** League of Legends game data is only available to a profile using the League of Legends module. General info is always available to all profiles.

# Creating a condition
Conditions are created using the [visual scripting system](/guides/user/profiles/nodes), this means all you need to do is click things!
The node script of a condition always has a single exit node called "Activate ..." that takes a boolean value, whatever you put in here indicates the end-result of the condition. 

Here is a simple example visual script that activates a layer when the time of day is after 17:00
![Example condition](https://i.imgur.com/EC7NIJv.png){.elevation-3 .radius-3}

## Layers and folders
In order to use display conditions on layers and folders you need to select an **activation type** that uses display conditions. This is done in the bottom-right corner of the editor when you've selected either a layer or a folder. To recap Artemis has four different types of display conditions, namely

- **Always**
The element is always active, this is the default type and does not use any kind of node script.
- **Once**
The element is shown once until its timeline is finished, this type also does not use any kind of node script.
- **Conditional**
The element is activated when the provided visual script ends in true.
- **On event**
The element is activated when the selected event fires.  
Events that contain data can conditionally trigger the layer using a visual script.

The two bottom ones allow you to define your own conditions.

### Simple conditions
Select the **Conditional** activation type and click on **Edit condition script**.
A new window will open in which you can create your condition script. The layer/folder remains active for as long as this visual script outputs `true` to the end node and finishes it's run when the value becomes `false`. You can tweak this behaviour with the other two options.

![Conditional activation type](https://i.imgur.com/ix985W3.png){.elevation-3 .radius-3}

### Event conditions
When picking the On event activation type, you must first select an event to trigger on before you can edit the condition script.
A new window will open in which you can create your condition script.   
The layer/folder will play its timeline once in response to the event if the visual script outputs `true` when the event triggers. You can tweak this behaviour with the other two options.

![On event activation type](https://i.imgur.com/DccmRQ9.png){.elevation-3 .radius-3}

In adittion to the exit condition scripts for event conditions also have a start node that outputs event data.  
The contents of this node depend on what you've selected in the **Triggered by event** option
![Event arguments](https://i.imgur.com/0AQW0l5.png){.elevation-3 .radius-3}

## Profiles
Acivation conditions for profiles work in exactly the same manner as the Simple conditions for folders and layers.
You can confire a profile's activate condition in the [sidebar](/guides/user/sidebar#activation-conditions). 