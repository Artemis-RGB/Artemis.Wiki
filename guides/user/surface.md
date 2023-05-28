---
title: Surface
description: A guide on what the surface is and how to set yours up correctly
published: true
date: 2023-04-01T23:58:19.384Z
tags: 
editor: markdown
dateCreated: 2020-12-21T14:43:49.816Z
---

**Not what you're looking for?**
Head back to the guide overview on the [getting started](/guides/user) page.
# Setting up the surface
During the initial startup wizard, you picked one or more device providers to use. These device providers have initialised in the background and made any devices they detected available to Artemis.

> Missing devices? Check out the [troubleshooting](/guides/user/troubleshooting) guide!
{.is-warning}

Now it's time to prepare your surface by giving these devices their own position. The surface contains a 2D representation of where all your devices are located in a physical space, like your desk or even entire room. 

When you first open the surface editor you'll notice Artemis already made an effort to lay your devices out for you. You can use this as a starting point.

![surface-editor-overview.png](/guides/user/surface-editor/surface-editor-overview.png =1000x){.radius-5 .elevation-3}

Now all you need to do is move devices around to match up with their real location as closely as possible. This is done by dragging them around like icons on a desktop, you can even select multiple devices at once by dragging a selection.

> Artemis uses this information for its spatial awareness, allowing effects to realistically move across multiple devices.
{.is-info}

> The box around the surface is the maximum size, on a render scale of 100% this is 4096x4096mm our roughly 160 inches. 
> If you ever need more you can increase it by decreasing the render size.
{.is-info}

## Advanced usage
![context-menu.png](/guides/user/surface-editor/context-menu.png =500x){.elevation-3 .radius-5 .align-right} To help you match your virtual surface as closely to the real life situation as possible, there are a few extra options you can use.

If you right-click a device a menu will open.
- Clicking **<i class="v-icon mdi mdi-alarm-light"></i> Identify** will make the device blink white a few times, that way you can tell the difference between similar devices.
- **<i class="v-icon mdi mdi-arrange-bring-to-front"></i> Bring to Front** and the other 3 options allow you to put certain devices on top of eachother, like RAM on a mainboard.
- **<i class="v-icon mdi mdi-gesture-double-tap"></i> Identify input** is used to teach Artemis which keys presses/mouse clicks belong to which device. This is irrelevant if you only have one mouse and keyboard.
- **<i class="v-icon mdi mdi-cog"></i> View properties** will bring up an options menu where you can precisely control the position in milimeters, change the scale and rotation of a device and apply color calibration.

Click and drag to select multiple devices at once (like in Windows explorer)

Hold <kbd>shift</kbd> to move devices on a 1 cm grid to easily align them

Hold <kbd>ctrl</kbd> to move devices on top of each other (overlapping LEDs is not recommended)

To move around the surface hold down <kbd>middle mouse button</kbd> and drag.

> Overlapping LEDs will cause light to bleed from one LED into another.
{.is-warning}


<div class="clearfix"></div>

## Color calibration
![device-properties.png](/guides/user/surface-editor/device-properties.png =500x){.elevation-3 .radius-5 .align-right} Some devices, especially across different manufacturers, may have slightly different color toning. Because of this, it is possible to apply color calibration to each induvidual device. That way you can adjust the colors of different devices until they closely match eachother.

In order to do this, right-click a device and select **<i class="v-icon mdi mdi-cog"></i> View properties**, a dialog showing the device properties will open.

On the right side you can use the sliders to adjust the red, green and blue values of the device. To try your calibration out with different colors, check **Show preview** and select a color in the color picker.

The changes you make will be shown straight away and clicking **Apply** will save them.

<div class="clearfix"></div>

With the surface set up you are ready to start exploring the rest of Artemis. 
A good next stop is the [modules](/guides/user/modules) page or head over to the guide overview on the [getting started](/guides/user) page.
