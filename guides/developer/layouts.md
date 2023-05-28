---
title: Device layouts
description: A guide on creating layouts for your devices
published: true
date: 2021-07-26T07:31:35.499Z
tags: 
editor: markdown
dateCreated: 2020-11-25T09:13:57.008Z
---

> Want to request a layout? Please create a request [here](https://github.com/Artemis-RGB/Artemis.Plugins/issues/new?assignees=&labels=layout-request&template=layout-request.md&title=%5BLayout+request%5D), someone may be willing to make one for you, but no guarantees!
{.is-info}


# Introduction
> This guide is still a work in progress.
{.is-warning}

For Artemis to fully support a device it needs two things:

1. A way to talk to the device (usually through an SDK)
2. Knowledge about how the device looks and where all the LEDs are.

The first requirement is very technical and requires programming skills but the second one, while it is a little tedious, does not.

The way you tell Artemis about the dimensions and LED positions of a device is through something called a **device layout**. 
In this guide we'll walk you through the steps to create your own device layout, how to use in in Artemis and how to share it so it may get included in Artemis, so everyone can enjoy your work!

The guide assumes you use the [RGB.NET layout editor](https://github.com/SpoinkyNL/RGB.NET-Layout-Editor) which you can download from GitHub [here](https://github.com/SpoinkyNL/RGB.NET-Layout-Editor/releases). 
This editor allows you to visually put together the layout for your device and will save you some time, especially on devices with lots of LEDs like keyboards.

If you'd rather create a layout manually in XML, take a look at the [RGB.NET guide](https://github.com/DarthAffe/RGB.NET/wiki/Creating-Layouts).

> The layout editor is not part of Artemis and it is kind of thrown together to avoid manually editing the layout files. Even so, if you run into issues with it feel free to contact us on Discord, in the #layouts channel.
{.is-warning}

# The basics
We'll go through the basics by creating a simple mouse layout. All other devices follow the same process so what you read here will apply to all of them.
Creating a **keyboard** layout requires some extra steps. Please refer to the keyboard chapter for more details.

## Load or create
When you open the editor you will be greeted by the welcome screen. From here you can choose to
1. **Load from XML** - This allows you to load one of the layouts included in Artemis
2. **Create new layout** - This lets you create a new layout.

While especially for keyboards I recommend basing your layouts on existing ones, lets create one from scratch first to see how that works.

Once you click **Create new layout** you'll be asked to pick a base folder.


> If you create your own layout be sure to not only store it in the Artemis plugin folder, **Artemis will remove it** when you update to a new version.
{.is-danger}


## Metadata
With your base folder selected you'll be shown the editor window. Everything is empty so lets first start by providing some metadata on the device you are creating a layout for.
In the table below you can find a description for all the fields, you can skip the image fields, we'll do those next.

| Field            | Description                                                                                                                                                                                                         |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name             | The name of the layout.                                                                                                                                                                                             |
| Author           | The author of the layout (added later, not visible in the screenshot).                                                                                                                                              |
| Description      | The description of the layout.                                                                                                                                                                                      |
| Vendor           | The name of the device-manufacturer.                                                                                                                                                                                |
| Model            | The exact model-name of the device.                                                                                                                                                                                 |
| Width            | The exact physical width in mm of the device.                                                                                                                                                                       |
| Height           | The exact physical height in mm of the device.                                                                                                                                                                      |
| Type             | The [type](https://github.com/DarthAffe/RGB.NET/blob/master/RGB.NET.Core/Devices/RGBDeviceType.cs) of the device.                                                                                                   |
| Image base path  | The base path from which to load device and LED images                                                                                                                                                              |
| Device image     | The path to the device image relative to the image base path                                                                                                                                                        |
| Image layout     | A collection of image layouts, used for keyboards with multiple different logical layouts                                                                                                                           |
| Default LED size | The default width and height of a led used for layout calculations. This value is optional with a default value of 19mm which should be correct for,standard keyboards. Other devices might need other values here. |


## Setting up device images
With the basics now entered we can set up our device images. In this example we'll create a layout for a mouse so all we need is one image of the mouse. 
If you are creating a keyboard layout the process different because it requires induvidual images for each key. Check out the keyboard images chapter for more info on that.

Finding a suitable image can be a little tricky. For Artemis, devices should be shown either top-down or from the front. 
Webshops are usually a good place to start looking, if your mouse comes with software you could perhaps get a good image from there.

You also need to make sure your image does not contain any backgroud. To remove the background you can use free software like [GIMP](https://www.gimp.org/), the free online tool [remove.bg](https://www.remove.bg/) (seriously, that one is black magic) or ofcourse, Photoshop.

> Make sure your image isn't too big both in file size and dimensions. Just make sure it looks sharp and **stays below 1 mb**. Otherwise we cannot include it with Artemis as the download size would get too big.
{.is-warning}

Before we can continue we need to select an image base path. This path is relative to the base folder you selected at the very start.
To keep things organized, the layouts included in Artemis store their images in an image subfolder followed by brand and device type.

For a Corsair mouse this becomes `Images\Corsair\Mice`.

After selecting the image base path we can select our image.  
The editor won't move the image for you, it should already be in the right place. In our example the full path to our image will be `%ProgramData%\Artemis\Plugins\Artemis.Plugins.Devices.Corsair\Images\Corsair\Mice\DARKCORERGB.png`

This is the image we'll use for the guide.
**One extra detail**: This image originally had the LED glowing but by simply applying a grayscale filter, it looks like the LED is off.

![darkcorergb.png](/guides/layouts/darkcorergb.png)

With the image selected we can finally see our mouse on the editor!

## Adding LEDs
With the image set up we now see where the LEDs should be positioned. The next step is figuring out which LEDs we need to add.
This ofcourse depends on your device. The mouse shown above has three lighting zones which we'll represent with three LEDs.

Now we need to know what these LEDs are called. While you can find this out through trial and error, Artemis can show you what LEDs a device has.
To do this, open up Artemis and head into **Settings** > **Devices**. Find your device and click the three dots and select **Device properties**. A new window will and the LEDs tab contains a table of all the LEDs. 

Sadly currently Artemis cannot help you identify which LED is which, you'll have to find that out by assigning colors to the LEDs in a new profile.

Once you are ready to add a LED, head back into the layout editor and click **Add LED before**, you'll then be asked to select a LED ID. This is the ID Artemis showed you. You can only use each LED ID once per device.

> In case you didn't know: You can type text in the dropdown to select an ID, so if you press **M** it'll select **Mouse1**. This actually works for any dropdown box in Windows but it's extra useful here because there are so many LED IDs.
{.is-info}

When you click **Add** your first LED will be added, but depending on your default LED size it might be a very tiny little dot.
![create_led_1.png](/guides/layouts/create_led_1.png){.elevation-3}
- Scale it up using the Width and Height properties of the LED so that it easily covers the entire LED on the mouse.
- You can move the LED around by modifying the X and Y values. 
- Hit **Apply** to view your changes

For the mouse we're working on in this guide, **Mouse1** is the scroll wheel LED, so lets make sure the LED covers the entire scroll wheel.
![create_led_2.png](/guides/layouts/create_led_2.png){.elevation-3}
We will repeat these steps for each LED on the mouse until we covered all three zones like so:
![create_led_3.png](/guides/layouts/create_led_3.png){.elevation-3}

You'll notice that **Mouse2** (in purple) is very tall. This is because the LED covers **two** physical LEDs on the mouse. Many devices including this one don't have seperate controls for every lighting zone and are therefore represented by a single LED.

### X and Y values
The X and Y values of a LED don't need to be a number, especially for devices with many LEDs it may be useful to look into the laternative options below:
   - `+` Sets the location to be directly after the previous led.
   - `+0` (0 can be any number) Sets the location to be after the previous led with a gap of the given size.
   - `=` Sets the led to the same location as the previous led.
   - `-` Sets the location to be directly before the previous led.
   - `-0` (0 can be any number) Sets the location to be before the previous led with a gap of the given size.
   - `~` Acts as `-` but not from the start but the end of the led.
   - `~0` (0 can be any number) Acts as `-0` but not from the start but the end of the led.   

The default mode is `+`.   
## Saving the layout
With the LEDs in place we can save this layout and test it in Artemis. 
Artemis has two ways of loading custom layouts

1. By selecting the custom layout in the device properties window
2. By placing the layout in user layouts folder, located in `%ProgramData%\Artemis\user layouts`

### Option 1
**Option 1** is most convenient and useful for testing as your layout is applied as soon as you load it, allowing you to make changes and reloading it.

- To use this option, save your layout wherever you like by navigating to **File** > **Save current layout**.
- Once you've done that open Artemis, go to **Settings** > **Devices**, click on the <i class="v-icon mdi mdi-dots-vertical"></i>-icon and open the device's properties.
- Under **Custom layout** click on the **Layout path** field to open up the file dialog and select your custom layout. It will be applied immediately.

If you've made changes, click the <i class="v-icon mdi mdi-close-circle"></i>-icon and reselect your layout.

### Option 2
**Option 2** is most useful if you have a custom layout for a device that's on your surface multiple times, like case fans or RAM sticks.

- To use this option, save your layout in `%ProgramData%\Artemis\user layouts` by navigating to **File** > **Save current layout**.
- Once you've done that open Artemis, go to **Settings** > **Plugins** and reload the plugin that provides your device(s).

> `%ProgramData%` is an alias for wherever your ProgramData folder is located, typically at `C:\ProgramData`. You can paste the path though, Windows will resolve it.
{.is-info}


This concludes the first part of the guide. We will come back to this layout and refine it further in the [custom LED shapes](#custom-led-shapes) chapter.

# Keyboard layout
Creating a keyboard layout requires some extra work compared to layouts for other device types. 
I recommend that you base your keyboard layout on an exising layout that roughly matches your keyboard. This saves you adding all the LEDs (in the case of a keyboard, the keys) in the right order.

## Setting up the layout
The first few steps are the same as described in the [basics](#the-basics) chapter with the exception that you'll probably want to load an existing layout and edit that instead.

# Custom LED shapes 
For many devices using rectangular LEDs gets the job done. But the finishing touch is using custom LED shapes to accurately recreate the LEDs on the device.

Lets get back to the mouse example from before:
![create_led_3.png](/guides/layouts/create_led_3.png){.elevation-3}

## Shape editing
Lets start with **Mouse1**, which in this case represents the scroll wheel.

*First we'll do the left side of the scroll wheel.*
- Set the Shape of Mouse1 to **Custom**
- Click on **Start shape edit**
- Click at various points in the LED to form a path
- When finished click on **Stop shape edit** (your path will be saved up till the last time you **clicked**)

When done you'll notice that shape data was added.
![custom_led_1.png](/guides/layouts/custom_led_1.png =880x){.elevation-3}

Now we need a second path for the right side of the scroll wheel. Click on **Start shape edit** again and repeat the process from before.

![custom_led_2.png](/guides/layouts/custom_led_2.png =880x){.elevation-3}

So every time you click start and stop, you get a new path in the same LED. If you want to start over just remove the path data and click Apply.

> I realise this feature is kind of crude but these paths do not need to perfectly line up as long as they give a good representation of the LED it's good enough. Creating path editing software is a lot of work for something so simple ;)
{.is-info}

## Using SVG imports
The logo on the mouse is quite intricate so let's instead import an SVG file of the Corsair logo for this. I went with the one found [here](https://worldvectorlogo.com/logo/corsair-3).

*The process of using an SVG is pretty simple*
- Make sure the Shape is set to **Custom** and click **Apply** first
- Click on **Import SVG** and select your SVG file
- Tweak the X, Y, width and height of your LED to line up the imported SVG as best you can

> The upside of this approach is that you can use software like [Inkscape](https://inkscape.org/) to create far more accurate paths using curves etc. While this isn't neccisary for most layouts, it's an option.
{.is-info}

After lining up the SVG nicely, this is the end result:
![custom_led_3.png](/guides/layouts/custom_led_3.png =880x){.elevation-3}