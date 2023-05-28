---
title: Data Model Nodes
description: The help page for the different data model nodes
published: true
date: 2023-02-12T17:35:18.697Z
tags: 
editor: markdown
dateCreated: 2023-02-12T17:13:30.249Z
---

# Introduction
The data model nodes form a set of nodes that give you access to the Artemis data model in different ways.
These nodes will likely form the basis of any of your condition and data binding visual scripts as they allow you to create profiles that respond to what's happening on your system, in your game or even smart devices in your house (check out the [Hue plugin](/guides/user/devices/philips)!)

![Data model nodes](https://i.imgur.com/s41lb4s.png){.elevation-3 .radius-3}

# Data Model-Value
This is the most straightforward node that simply outputs the current value of whatever data model path you've selected.

![Data model nodes](https://i.imgur.com/FrEMtCX.gif){.elevation-3 .radius-3}
In this example the Data Model-Value node outputs the peak volume.  
In combination with a static Numeric node and Greater than node you could make a layer react to loid noises.

#### Output
The node has a single output pin containing the current value of whatever data model path you've selected.
The type of the pin changes depending on the data model path you've selected.

# Data Model-Event
(TODO)
This node outputs the latest data of a data-model event

![Data model nodes](https://i.imgur.com/stXEhh5.gif){.elevation-3 .radius-3}

# Data Model-Event Value Cycle
This node cycles through whatever values you put into it each time the event you select fires.

![Data model nodes](https://i.imgur.com/NP7tI3q.gif){.elevation-3 .radius-3}
In this example the node switches from red to green to blue each time a key is pressed.

#### Input
A collection of values through which the node cycles, switching to the next input pin each time the selected event fires.
The type of all pins change depending on the first type you connect to the input pins.

#### Output
The node has a single output pin that contains the value of one of the input pins, switching to the next input pin each time the selected event fires.
The type of pin changes depending on the first type you connect to the input pins.