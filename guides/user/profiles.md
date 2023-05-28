---
title: Profiles
description: This guide will introduce profiles and walk you through the different elements of the editor, explaining in short what everything is used for.
published: true
date: 2023-04-01T23:58:19.384Z
tags: 
editor: markdown
dateCreated: 2020-11-09T13:52:29.483Z
---

**Not what you're looking for?**
Head back to the guide overview on the [getting started](/guides/user) page.
# Introduction
The main purpose of this guide is to be an overview of what features are available and what they're used for.

The profile system is one of the main features of Artemis and is what allows you to create extremely customizable effects on all your supported devices. Profiles are closely tied to [modules](/guides/user/modules), this means each profile you create is a profile for a module. You can create multiple profiles and switch between them at will as long as the module is active. 

Since all changes to profiles are made using the **profile editor**, every profile feature is shown through the editor. However, this guide won't go into deep detail of each individual feature, instead links to more specific guides will be included where relevant.

**To access the profile editor of a module, simply select the module in the sidebar.**  

# Profile contents
A profile contains your layers and folders, it is basically Artemis's way of storing your savedata.
Profiles conform to a hierarchy as shown below:

- **Folders** - Your profile can contain as many folders as you want
  - *Folders may contain other folders and layers, nesting the hierarchy*
- **Layers** - Your profile can contain as many layers as you want
  - **Properties** - Each layer has its own set of properties
    - **Keyframes** - Keyframes allow you to change the values of properties over time
    - **Data bindings** - Data bindings allow you to bind the values of properties to data such as CPU usage, health bars etc.
  - **Brush** - A layer uses a brush to **determine** what should be shown
    - **Brush properties** - Each brush has its own set of properties
  - **Effects** - A layer can use effects to **modify** what should be shown
    - **Effect properties** - Each effect has its own set of properties
  - **Conditions** - Conditions allow you to show/hide layers when specific criteria are met.
# The editor
The profile editor is accessed by selecting a module in the sidebar, you'll be in the profile editor for that specific module. 

> Once you open the profile editor regular profile playback stops, all other modules are suspended and the editor takes over.
{.is-warning}

The image below highlights each aspect of the profile editor. In the next chapters each highlighted part of the editor is explained.
![overview.png](/guides/user/profiles/overview.png){.elevation-3 .radius-5}

## Toolbox
The toolbox contains all the tools you can use to modify layers in de visualization panel on the right.
**The tools available to you are:**

- **<i class="v-icon mdi mdi-hand-left"></i> Panning tool** - Use this to pan around the profile, you can quickly access this by holding down <kbd>Ctrl</kbd>.
- **<i class="v-icon mdi mdi-transit-connection-variant"></i> Transform tool** - Use this to transform the shape of the currently selected layer.
- **<i class="v-icon mdi mdi-selection-drag"></i> LED selection tool** - Use this to change the LEDs of the currently selected layer.
- **<i class="v-icon mdi mdi-select-off"></i> LED removal tool** - Use this to remove LEDs from the currently selected layer.

More detailed info on using these tools can be found in the layer guide.

## Visualization
The visualization part of the editor is used to see what's going on in real-time. Assuming your devices have a layout, you'll see a realistic representation of your device with all its LEDs. 

You can use the Panning tool to move around the surface (holding down <kbd>Ctrl</kbd> will select the panning tool until you release it again). To get a closer look you can use the mousewheel to zoom in and out.

The visualizer shows all the layers of your profile but only LEDs and shape of the currently selected layer are highlighted. 
Below is an example of 3 layers - all on the keyboard - but with shapes that cover only part of the keyboard:  
![multiple-layers.png](/guides/user/surface-editor/multiple-layers.png){.elevation-3 .radius-5}

How layers and their shapes exactly work is discussed in the [layers guide](/guides/user/profiles/layers).{.caption}

## Profile elements
![profile-elements.png](/guides/user/profiles/profile-elements.png){.elevation-3 .radius-3 .align-right}Just above the panel you can manage your profiles for this module such as adding new ones, switching profiles, renaming etc.. The profile elements panel itself contains all the layers and folders of your profile.  

Each element contains an icon indicating its type, a <i class="v-icon mdi mdi-folder"></i> or <i class="v-icon mdi mdi-folder-open"></i> for folders and a <i class="v-icon mdi mdi-layers"></i> for layers.
For layers another icon is visible which is the brush icon. This icon helps you to more easily identify layers, hovering over this icon will also tell you the name of the brush.
You can use the <i class="v-icon mdi mdi-eye"></i>-toggle to temporarily disable layers and even entire folders.

The main purpose of this panel is to manage the contents of the profile
- Click either the <i class="v-icon mdi mdi-folder-plus"></i>-icon or the <i class="v-icon mdi mdi-layers-plus"></i>-icon to add a new element to the profile root.
- Right-click a folder to open a context menu allowing you to add a new element.
- Copy/paste an existing element by right-clicking it or using <kbd>Ctrl</kbd> + <kbd>V</kbd> and <kbd>Ctrl</kbd> + <kbd>C</kbd>.
- You can change the order of elements by dragging them around. 
- You can also move existing elements into a folder by dragging that element into the folder.
- Right-clicking any element will give you even more options like renaming, deleting etc.

<div class="clearfix"></div>

## Playback controls
> It is vital to understand that these controls are only for the profile editor. **Nothing** you click here effects **regular** profile playback in any way.
{.is-warning}

![playback-controls.png](/guides/user/profiles/playback-controls.png){.elevation-3 .radius-3 .align-right}To get a sense of how your profile will look when the editor is closed, you can use the playback controls to start a preview.
- **<i class="v-icon mdi mdi-step-forward"></i> Play from start** - Previews the current layer from the start. - <kbd>Shift</kbd> + <kbd>Space</kbd>
- **<i class="v-icon mdi mdi-play"></i>/<i class="v-icon mdi mdi-pause"></i> Play/pause** - Play or pause the current preview. - <kbd>Space</kbd>
- **<i class="v-icon mdi mdi-skip-backward"></i> Go to start** - Moves the timeline cursor to the start of the layer.
- **<i class="v-icon mdi mdi-skip-forward"></i> Go to end** - Moves the timeline cursor to the end of the layer.
- **<i class="v-icon mdi mdi-skip-previous"></i> Previous frame** - Moves the timeline cursor back one frame.
- **<i class="v-icon mdi mdi-skip-next"></i> Next frame** - Moves the timeline cursor forwards one frame.
- **<i class="v-icon mdi mdi-repeat"></i>/<i class="v-icon mdi mdi-repeat-once"></i> Repeat** - Toggles repeating the current layer (if set to <i class="v-icon mdi mdi-repeat"></i>) or the current segment (if set to <i class="v-icon mdi mdi-repeat-once"></i>) **during preview**.
	- *To learn about repeat modes for layers during **regular** profile playback, see the [timeline guide](/guides/user/profiles/timeline) and more specifically the [segments guide](/guides/user/profiles/timeline/segments).*
- **00.350** - The current position on the timeline.

## Properties & effects
![layer-properties.png](/guides/user/profiles/layer-properties.png){.elevation-3 .radius-3 .align-right}When you select a layer in the profile elements panel, its properties become visible in the properties panel.
Because this guide is meant as an overview, we won't go into detail here but the main takeaway is that this is where you change all the settings for your layer.

In a new layer all settings are collapsed, you may expand them by clicking the <i class="v-icon mdi mdi-chevron-right"></i>-icon. Once you've done that you'll be shown all the settings within that category.

By default a layer has 3 main categories
- **<i class="v-icon mdi mdi-hammer-wrench"></i> General** - The most important property here is the **Brush type**. This determines what is actually shown in your layer.
- **<i class="v-icon mdi mdi-transit-connection-variant"></i> Transform** - These properties all allow you to change the shape of your layer. You can also manipulate these properties using the [transform tool](#toolbox).
- **<i class="v-icon mdi mdi-brush"></i> Brush** - The third category contains all the properties of the brush you selected under general. These properties are different for every brush.

<div class="clearfix"></div>

> Already want to learn a bit more? Hover over the properties in Artemis to view a more detailed description of what they do!
{.is-info}

Below the properties you can see the name of the currently selected layer and next to that there's an **ADD EFFECT** button. Clicking this button will allow you to add an effect to the layer.
A layer can use effects to modify what should be shown, this can be adding a glow, adjusting the color, making the layer grayscale etc. 

You can have multiple effects but they are always applied in order. 
Because when stacking effects the order can make a difference, you can reorder effects by dragging them up and down.
![layer-effects.png](/guides/user/profiles/layer-effects.png){.elevation-3 .radius-3}

Each effect has its own property group but they are slightly different from the 3 main categories
- The <i class="v-icon mdi mdi-eye"></i>-toggle is used to temporarily disable effects.
- The <i class="v-icon mdi mdi-rename-box"></i>-icon lets you rename an effect (this is useful if you have per example multiple color corrections)
- The <i class="v-icon mdi mdi-trash-can"></i>-icon lets you delete an effect.

For more info on properties and effects, please refer to the [layers guide](/guides/user/profiles/layers).

## Timeline
The main purpose of the timeline is to create custom animations using <i class="v-icon mdi mdi-timer"></i> keyframes. 

The timeline allows you to change the value of one or more properties over time. The way this is done is by giving a property multiple values at different points in time, these values are called keyframes. When the timeline plays Artemis smoothly follows these keyframes, resulting in an animation.

The timeline is split up into separate rails. **Each property has its own rail** and on these rails you can place keyframes. Because of this, you'll be using the properties panel and the timelines panel together a lot.

![timeline.png](/guides/user/profiles/timeline.png){.elevation-3 .radius-3}
In the image above you'll see that keyframes are enabled for the **Position**, **Scale** and **Rotation** properties. This was achieved by clicking the <i class="v-icon mdi mdi-timer"></i>-icon in front of each property.

Each keyframe is shown on the timeline using circle like this one: <i class="v-icon mdi mdi-checkbox-blank-circle" style="color: #009688"></i>. 
You can drag these around to change their position. The position of your keyframes determine the **start**, **end** and **speed** of the animation.

Changing the value of a property which has keyframes enabled adds a new keyframe at the current position of the timeline cursor. 

Collapsing a property will also collapse the rails, causing all keyframes to be consolidated into a single rail which you cannot edit.
![timeline-collapsed.png](/guides/user/profiles/timeline-collapsed.png){.elevation-3 .radius-3}

To learn about the timeline and keyframes, see the [timeline guide](/guides/user/profiles/timeline) and more specifically the [keyframes guide](/guides/user/profiles/timeline/keyframes).

## Conditions
In Artemis you can use conditions to make layers and even entire folders hide/display when certain criteria are met. 

Conditions are created using visual programming, this means all you need to do is click things!
Below is an example of a condition using groups and different operators.
![conditions.png](/guides/user/profiles/conditions.png){.elevation-3 .radius-3}

Conditions are color coded and can be devided into several parts
- <strong style="color: #E74C4C">Red</strong> is the boolean operator (and, or, and not, or not)
- <strong style="color: #AB47BC">Purple</strong> is the left side of the condition (any data model value)
- <strong style="color: #7B7B7B">Gray</strong> is the comparison operator (equals, does not equal, is greater than etc.)
-  <strong style="color: #009688">Teal</strong> is the right side of the condition (any data model value or your own input)

**Since the right side of the condition can be a data model value or your own input, you can swap between the two modes by clicking the <i class="v-icon mdi mdi-swap-horizontal"></i>-icon.**

In full human language the condition from the image above looks like this:
<kbd style="background: #AB47BC">The day of the week</kbd> <kbd style="background: #7B7B7B">is</kbd> <kbd style="background: #009688">monday</kbd> <kbd style="background: #E74C4C">and</kbd> <kbd style="background: #AB47BC">the current hour</kbd> <kbd style="background: #7B7B7B">is before</kbd> <kbd style="background: #009688">17:00</kbd> <kbd style="background: #E74C4C">or</kbd> <kbd style="background: #AB47BC">The day of the week</kbd> <kbd style="background: #7B7B7B">is</kbd> <kbd style="background: #009688">friday</kbd> <kbd style="background: #E74C4C">and</kbd> <kbd style="background: #AB47BC">the current hour</kbd> <kbd style="background: #7B7B7B">is or is later than</kbd> <kbd style="background: #009688">12:00</kbd>

---
Below the conditions you'll find two configuration options, the **Play mode** and the **Stop mode**. 
These allow you to configure how your layer should act while its conditions are met and when conditions stop being met.

**Play mode** - Configure how the layer should act while the conditions are met
- **<i class="v-icon mdi mdi-repeat"></i> Repeat** - Continue repeating the timeline while the condition is met.
- **<i class="v-icon mdi mdi-timer-outline"></i> Once** - Only play the timeline once when the condition is met.

> Want your layer to repeat, even while you have no conditions? Make sure play mode is set to **<i class="v-icon mdi mdi-repeat"></i> Repeat**. 
{.is-success}

**Stop mode** - Configure how the layer should act when the conditions are no longer met
- **<i class="v-icon mdi mdi-play-outline"></i> Finish** - Finish the the current run of the timeline when the conditions are no longer met.
- **<i class="v-icon mdi mdi-skip-next-outline"></i> Skip to end** - Skip to the end of the timeline when the conditions are no longer met.

More details on conditions, different condition types and more can be found in the [conditions guide](/guides/user/profiles/conditions).

## Data bindings
One last powerful feature of the editor are data bindings. Where conditions allow you to show/hide things based on certain criteria, data bindings allow you to *tie properties to values*.

To show the difference we have two examples
- **Conditions**: Show a red blinking layer when you are low health, creating a health alert.
- **Data bindings**: Bind the width of a layer to your current health percentage, creating a health bar.

