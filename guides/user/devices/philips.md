---
title: Philips Hue
description: An overview of the Philips Hue integration offered by the Hue plugin
published: true
date: 2020-11-18T08:40:07.901Z
tags: philips hue, hue, plugin, device, data model expansion
editor: markdown
dateCreated: 2020-11-17T19:34:05.875Z
---

# The Artemis Hue plugin
![hue-logo.png](/guides/user/devices/philips/hue-logo.png){.align-abstopright}Artemis offers [Philips Hue](https://www.philips-hue.com/) support through the built-in Hue plugin as long as you are using a Hue Bridge.
Once set up the following features are supported

- Datamodel support
	- Rooms
	- Zones
	- Lights 
		- On/off state
		- Color
		- Brightness
	- Sensors
		- Switches
			-	Button press events
			- Which button was pressed
			- When the last button was pressed
		- Motion sensors
			- Motion detection events
			- When motion was last detected
			- Light levels
			- Daylight detection
			- Temperature
- Device provider support (**only with Hue Bridge v2**)
	- Realtime control of all the lights in a room using the [Hue Entertainment mode](https://www.philips-hue.com/en-gb/explore-hue/propositions/entertainment)

## Combining the Hue colors and Artemis
It is possible to still control the colors of your Hue lights (somewhat) regularly while Artemis is connected to them.

The way you do this is by creating a seperate layer for each light and databinding the color of that **layer** to the color of the **Hue light**.
This works because while Artemis controls the lights realtime this does not update the actual colors of the lights in Hue.

So, once you've created a layer for each light you can now put regular layers on top. When those layers are not being shown, the lights will revert to their Hue colors.

> Unfortunately the Hue app won't let you open rooms that are controlled by Artemis. To get around this, open the room _before_ opening Artemis.
> Other third party apps may work better, [Hue Essentials](https://play.google.com/store/apps/details?id=com.superthomaslab.hueessentials) per example lets you control the entire room while Artemis is controlling it.
> The physical Hue Smart Dimmer and similar producs do seem to work fine.
{.is-warning}
