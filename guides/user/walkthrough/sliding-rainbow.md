---
title: Sliding rainbow
description: A walkthrough for creating the holy grail of RGB effects
published: true
date: 2021-02-05T20:29:02.641Z
tags: 
editor: markdown
dateCreated: 2020-12-22T08:35:10.121Z
---

# Introduction
![puking-rainbows.jpg](/guides/user/walkthrough/puking-rainbows.jpg =x200){.radius-3 .align-left} Welcome to the sliding rainbow walkthrough! 
In this walkthrough we'll be creating the Crème de la Crème of RGB effects; the rainbow that moves.

<div class="clearfix"></div>

# Steps
Lets get started, follow these steps one-by-one and you'll be done in no time.

## Create a new profile
The first thing we need is a profile which houses the rainbow layer. 
To create a new profile simply open up the profile editor of any module, we'll use the **General module** for this guide.

![select-module.png](/guides/user/walkthrough/sliding-rainbow/select-module.png){.elevation-3 .radius-3}

With the General module selected, lets create a new profile by clicking the <i class="v-icon mdi mdi-plus"></i>-icon in the top-right corner.
Once you've clicked that, give your profile a name and click **ACCEPT**.
![profile-create.png](/guides/user/walkthrough/sliding-rainbow/create-profile.png){.elevation-3 .radius-3}

## Creating a layer
With your new empty profile in place you can now add a layer. For this guide we only need one that covers everything.
By clicking the <i class="v-icon mdi mdi-layers-plus"></i>-icon in the Profile elements panel, a new layer is added that covers the entire surface.

![create-layer.png](/guides/user/walkthrough/sliding-rainbow/create-layer.png){.elevation-3 .radius-3}

After you've clicked that, a new layer is created that uses the default solid color brush with a <strong style="color: red">red</strong> color.
![red-brush.png](/guides/user/walkthrough/sliding-rainbow/red-brush.png =x700){.elevation-3 .radius-3}

## Setting up the brush
Because a solid red color isn't what we're after, lets change the brush of the newly created layer. 
This is done by expanding the **<i class="v-icon mdi mdi-hammer-wrench"></i> General** properties and changing the **Brush type** to **<i class="v-icon mdi mdi-gradient"></i> Linear Gradient**.
![brush-type.png](/guides/user/walkthrough/sliding-rainbow/brush-type.png){.elevation-3 .radius-3}

With the linear gradient brush selected we'll immediately be greeted by a nice rainbow on our devices.
You'll also notice that in the properties list, there's a new entry: **<i class="v-icon mdi mdi-gradient"></i> Brush - Linear Gradient**. Expanding that entry will give us more control over our gradient.

- Clicking the gradient behind the **Colors** property will let you edit the colors used in the gradient.
- If you want the gradient to repeat itself, try increasing the **Colors multiplier** value.
- The **Rotation** value will allow you to tilt your gradient, a 10 degree angle can give a neat effect like this:
![tilted.png](/guides/user/walkthrough/sliding-rainbow/tilted.png =x300){.elevation-3 .radius-3}

## Animating the gradient
Right now we have a rainbow that doesn't move, that's not very interesting. Instead, it would be nice if the gradient scrolls by, repeating itself over and over.
To do this you have two options, using the **Scroll Speed** property or using **Transformations**. The first option is the simplest so if you just want quick results, stick with that :).

### Option 1. The scroll speed property
The linear gradient brush offers a scroll speed property which moves the gradient on the X- and Y-axis at a configurable speed in centimeters per second.
The plus side of this approach is that it is easy to set up and the gradient will seamlessly wrap around at the end, creating an endless loop.

### Option 2. Transformations
The second option is using a transformation to reproduce what the scroll speed property is doing. 
This is a little more involved and pretty overkill for what we're trying to achieve but because transformations are so versatile, it is good to know.


