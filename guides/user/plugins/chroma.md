---
title: Chroma Plugin Guide v1 05.2021
description: Introduction on how to setup the Chroma Profiles in Artemis
published: true
date: 2021-05-22T15:58:19.971Z
tags: 
editor: markdown
dateCreated: 2021-05-19T20:32:57.660Z
---

This is a guide to help you get [Chroma Workshop Games](https://www2.razer.com/chroma-workshop-games) RGB lighting profiles to work within Artemis using the [Chroma Plugin](https://github.com/diogotr7/Artemis.Plugins).

> Pre Requisites:
> - Synapse SDK and Connect module is installed and up to date.
{.is-warning}


## Plugin Installation

First, we need to download the [Chroma Plugin](https://github.com/diogotr7/Artemis.Plugins) and install it to Artemis. Go to the Settings <i class="v-icon mdi mdi-cog"></i>, and then to Plugins, and click Import Plugin ![settingsimportplugin1.png](/screenshots/chroma/settingsimportplugin1.png)

![settingsimportplugin.png](/screenshots/chroma/settingsimportplugin.png)


Once you've chosen the plugin file you've just downloaded, click open and you will then return to the main window with the plugin that you've just installed highlighted.

![settingspluginsimport_completechromahighlighted.png](/screenshots/chroma/settingspluginsimport_completechromahighlighted.png)

## Profile Setup

Now, once you've done this (and the plugin and it's features are Enabled) lets create a new Layer Folder so let's head on to our General Module under Normal.

![defaultviewhighlightgeneralprofile.png](/screenshots/chroma/defaultviewhighlightgeneralprofile.png)

Now, with your profile selected at the top, lets add a New Folder <i class="v-icon mdi mdi-folder-multiple-plus"></i> so that we can keep these layers organised and we will call it Chroma so we know that this will be where we store our Chroma Layer.

![defaultviewhighlightaddnewfolder.png](/screenshots/chroma/defaultviewhighlightaddnewfolder.png)

###### Note
You can add this layer to an existing profile, just make sure that you add a Display [Condition](/guides/user/profiles/conditions), more about this later.

Now that we've added the Folder, lets add 2 new layers. <i class="v-icon mdi mdi-layers-plus"></i>

![defaultviewhighlightaddnewlayer.png](/screenshots/chroma/defaultviewhighlightaddnewlayer.png)

Move these two layers into the newly created folder, and lets rename them. Rename the Top most layer as "Chroma Effect" and the bottom most layer as "Background". 

## Layer Setup

Now, lets edit our newly created Chroma Layer first. Select the 'Chroma Effect' layer and in the effect panel, under General>Brush type, choose 'Chroma Grabber Layer'.

![defaultviewchromagrabberlayer.png](/screenshots/chroma/defaultviewchromagrabberlayer.png)

For our second layer, we need to choose a solid background so that nothing will "leak-through" if you have any other Layers inside this profile. For this, we select the 'Background' layer, and again under General>Brush Type and this time we choose 'Solid'. This time, under Brush - Solid>Colour lets choose Black (normally a good choice).

![defaultviewbackgroundlayer.png](/screenshots/chroma/defaultviewbackgroundlayer.png)

## Setting Conditions

The final thing we can do to ensure that this layer is only activated when Chroma detects a RGB Enabled game is to add a condition to the Folder.

To do this, highlight the Chroma folder in Profile Elements and in Display Conditions click on the green plus<i class="v-icon mdi mdi-plus"></i>.

![defaultviewdisplayconditions.png](/screenshots/chroma/defaultviewdisplayconditions.png)

Now, we want to choose 'Add Condition'

Now, it will populate three small coloured boxes in the Diplay Conditions section and these colours are Pink Grey & Green.

What we need to do here is click the Pink box and goto 'Chroma Grabber' and select 'Current Application' then click the grey box and select 'Is Not Null'.

![defaultviewdisplayconditionsset.png](/screenshots/chroma/defaultviewdisplayconditionsset.png)

That's it! You're done - all you need to do it launch a Chroma Workshop compatible game and the profile will project on your peripherals!

## Advanced Options

Here are some tips that you can do if your chroma layer is not display as you expect it to on your devices.

I've seen this commonly happen on non-Razer devices as it really depends on your devices, in my example that I have used, you can see that I am using a Corsair Keyboard, Mouse, Mouse Mat and Headset and I am also using a DMX controller via [WLED](https://wled.me). This meaning that I do not own any of the Razer products but can still use the Chroma Workshop profiles on any relevant games.

Now, as my devices are not Razer Chroma Enabled, this does not mean that the profiles won't work - sometimes they need just a little direction....

[IMG]

Above you can see that I have many layers setup over my peripherals and LED Strip. The reason I do this is because the Chroma Layers do not all show on my devices, so as a work around I've added a [Data Binding](/guides/user/profiles/data-bindings) into seperate layers. This enables me to drill into Chroma, via the Chroma Layer Grabber, and select the specific LED effect to a section of my LEDs.

To have this work, all we need to do is add a new Solid Colour layer and link it directly back to a Layer from the Chroma Layer Grabber from the Data Model, you can see all of Artemis Data Models in real time by opening up the debugger window and browsing to the Data Model window.

[IMG]

Now that we've added a new layer (you can add as many as you need) let's use the tools on the left panel to decipher which LEDs each Layer controls whether you're adding, removing or transforming.

[IMG]

Next, open the Debug panel and go to the Data Model tab at the top and expand the Chroma Grabber Layer. Here we are going to look at the LED's and what the Chroma Grabber is showing us.

###### Note
Will need a active Chroma Workshop game running

[IMG]

Here you can see each