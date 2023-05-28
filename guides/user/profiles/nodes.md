---
title: Nodes System
description: An introduction page to Artemis's visual node scripting system
published: true
date: 2023-02-12T15:52:14.727Z
tags: 
editor: markdown
dateCreated: 2022-08-20T16:54:39.861Z
---

**Looking for something more specific?**
- [Conditions](/guides/user/profiles/conditions) - This guide will how you how you can create and combine multiple regular conditions.
- [Data Bindings](/guides/user/profiles/data-bindings) - This guide will explain special list-based conditions.

Alternatively, head back to the guide overview on the [getting started](/guides/user) page.

# Introduction
In Artemis it's possible to define custom logic using the visual scripting system.  
This system uses nodes that have one or more inputs and outputs which allows you to create both simple and very advanced data flows.

Nodes are used in both [conditions](/guides/user/profiles/conditions) and [data bindings](/guides/user/profiles/data-bindings), allow you to make your profile interactive.

![display-condition.png](/guides/user/nodes/display-condition.png){.elevation-3 .radius-3}
*An example node script that activates a layer when the player has a certain wanted level in GTA:V*

In the example above there are 4 nodes that together determine whether a layer should be activated.
- The **Data Model** node has an output pin (green) outputting the current wanted level of the player
- The **Numeric** node has an output pin (green) outputting the value entered in the numberbox
	- Both values are entered into the two input pins (white) of the **Greater Than** node
  - The **Greater Than** node outputs true or false (red) depending on whether the top value is greater than the bottom value
  	-	The resulting value is entered into the final **Activate Layer** node which determines whether the layer should be activated or not


# The editor
The editor shows all the nodes of your visual script
- Each node has one or more input (left) and output (right) pins
- A node may also contain pin collections, to these you can freely add/remove extra pins
- Some nodes contain extra UI elements, such as input fields

## Accessing the editor
The editor is used to create visual scripts, depending on where you want to use nodes there are two ways to access the editor
### Conditions
1. Select a layer and pick either the **Conditional** or the **Event** activation type
2. Click the **Edit condition script** button

### Data Bindings
1. Select a layer, find the property you want to create a data binding for and click on the <i class="v-icon mdi mdi-vector-link"></i>-button
2. On the newly opened panel, click the toggle next to the property name to enable data bindings
3. A small visual editor opens, you can also open the full editor by clicking the <i class="v-icon mdi mdi-open-in-new"></i>-button

## Using the editor
The editor uses a canvas in which you can freely rearrange your nodes in a way that makes sense for you. Try to avoid overlapping nodes or crossing paths to keep things easy to follow.
### General
- Pan around the canvas pressing middle mouse button, zoom in and out by scrolling
- Right-click to add a node at your current position
- Click and drag to select multiple nodes
- <kbd>Del</kbd> to delete the current selection
- <kbd>Ctrl</kbd> + <kbd>D</kbd> to duplicate the current selection (does not copy connections)

### Connections
- Click and drag on a pin to connect it to another pin via a cable
	- The colors indicate the type and have to match
  - White pins can take any color
- An output pin can connect to multiple input pins
- An input pin can only connect to one output pin
- Use middle mouse button to disconnect a pin
- Drop a cable in empty space to easily create a compatible node

### Reading values from the data model
To read values from the data model right-click and add the **Data-Model-Value** node.
Click on **Click to select** and pick a value from the data model. Once you've picked a value the output pin will change color to reflect the type of value you've chosen.


### Types of values
The visual scripting system uses colors to differentiate between types of data. This is required because you can't, for example, turn a number into a color.
- [<i class="v-icon mdi mdi-circle" style="color: #CD3232"></i> *boolean value - true or false*](#)
- [<i class="v-icon mdi mdi-circle" style="color: #FFD700"></i> *text*](#)
- [<i class="v-icon mdi mdi-circle" style="color: #32CD32"></i> *number*](#)
- [<i class="v-icon mdi mdi-circle" style="color: #AD3EED"></i> *color*](#)
- [<i class="v-icon mdi mdi-circle" style="color: #00B2A9"></i> *color gradient*](#)
- [<i class="v-icon mdi mdi-circle" style="color: #ED3E61"></i> *list - a list of multiple items*](#)
- [<i class="v-icon mdi mdi-circle" style="color: #1E90FF"></i> *enum - a choice from a predefined set, per example a team or a category*](#)
- [<i class="v-icon mdi mdi-circle" style="color: lightgray"></i> *any - takes any value, this is only for input pins*](#)
{.links-list}

There are nodes to turn one type of value into another, per example the Color Ramp node lets you turn a number between 0.0 and 1.0 into a color picked from a gradient.

![color-ramp.png](/guides/user/nodes/color-ramp.png){.elevation-3 .radius-3}
