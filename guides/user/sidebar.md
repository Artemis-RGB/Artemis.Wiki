---
title: Sidebar
description: A guide on how to use the Artemis sidebar to create and organize profiles.
published: true
date: 2022-10-06T19:05:16.864Z
tags: profiles, sidebar, guide
editor: markdown
dateCreated: 2021-07-08T12:22:18.246Z
---

**Not what you're looking for?**
Head back to the guide overview on the [getting started](/guides/user) page.
# Introduction
![sidebar.png](/guides/user/sidebar/sidebar.png){.align-right .elevation-3 .radius-5} So far you've probably used the sidebar to get around the different pages of the application such as the [surface editor](/guides/user/surface) and the [settings](/guides/user/settings) page. This is however just the static part of the sidebar which you cannot change. 

Below the settings button starts the customizable segemnt of the sidebar. In here, you can create your own categories and fill them up with profiles as you see fit.

# Categories
Categories are used to help manage profiles. If you use Artemis with a lot of different games/applications it may be usedful to put these in a separate category which you can collapse and suspend with one click.

You can create a category by clicking the **Add new category** button.

### Editing categories
You can edit a category by hovering over it and clicking on the <i class="v-icon mdi mdi-cog"></i>-icon or right-clicking the name. From here you can rename or delete the category. Note that deleting a category will also delete any profiles in that category.

### Category states
Categories only have two states: **active** and **suspended**. A category can be suspended using the <i class="v-icon mdi mdi-eye"></i>-button. When you do so, the category name will be struckthrough and all profiles in that category become **inactive**.

# Profiles

## Creating a profile
To create a profile hover over the name of a category in which you want to place the profile and click on the <i class="v-icon mdi mdi-plus"></i>-icon and choose **<i class="v-icon mdi mdi-plus"></i> Add new profile**.

From there the Add new profile dialog will open and you may pick a name for your profile. Each other option will be explained below.

### Module
A module is a type of plugin that provides Artemis with extra data. Some modules are always available and can be used by all profiles but others are not. **The ones that aren't always available are typically tied to an application or game.** 

This option is optional and will bind your profile to one of those modules, making the data of that module available to the new profile **but also making this profile only available when the module is active**.

This means that whenever you pick a module to bind your profile to, your profile will take on the activation conditions of that module (this is also shown in the dialog's **Activation conditions** region).

### Icon
To help you easily differentiate your profiles you can pick an icon. Artemis makes it's own Material Design icon library available for you to pick from.

If you want you can also pick a custom icon either based on a **bitmap image** (such as PNG, JPEG) by changing the **Icon type**. Artemis doesn't currently enforce a filesize on the icon, so be sure not to pick a giant wallpaper. ;)

### Hotkeys
Hotkeys are used to quickly suspend/unsuspend your profile with the press of a button. These hotkeys work even when Artemis is running in the background.

You can chose to have a single hotkey that toggles the profile, or a separate enable and disable hotkey.

To edit the hotkey simply focus the input and press the key combination you want to use. You can use any combination of modifiers such as <kbd>ctrl</kbd>, <kbd>alt</kbd> and <kbd>shift</kbd>.

### Activation conditions
Activation conditions are used to automatically activate and deactivate a profile based on a set of rules defined by you.  
You can customize the condition by clicking on **Edit condition script**.

![activation-condition](/guides/user/sidebar/activation-condition.png){.elevation-3 .radius-5}

The conditions make use of the node system, [a full guide is available here](/guides/user/profiles/nodes). To keep things short in this guide I'll set up two popular examples.

#### Enabling a profile when a certain application is running
This condition will enable the profile when a process named **'Photoshop'** is running, it doesn't need to be in the foreground. 


![running-process.png](/guides/user/sidebar/running-process.png =945x){.elevation-3 .radius-5}

#### Enabling a profile when a certain application has focus
This condition will enable the profile when the active window is from a process named **'Photoshop'**, so it needs to be in the foreground. 
![active-window.png](/guides/user/sidebar/active-window.png =945x){.elevation-3 .radius-5}

> Note that in both examples **.exe** was not included. That's because the process name isn't the same as the file name, which contains **.exe**.
{.is-warning}


## Managing profiles
### Editing profile properties
You can edit a profile's properties by hovering over it and clicking on the <i class="v-icon mdi mdi-cog"></i>-icon. From here you can access the same properties as when you created the profile.

To open the profile editor and start creating effects, simply click on the profile.

### Profile states
Profiles have three different states. You can have any amount of profiles in any of these states.

The different profile states are:
1. **Active**
An active profile is a profile that is currently being played.
2. **Inactive**
A incatvite profile is not being played because it's activation conditions aren't met, its name will be dimmed.
3. **Suspended**
A suspended profile has been disabled using the <i class="v-icon mdi mdi-eye"></i>-button on a hotkey, its name will be struckthrough.

> Multiple profiles can be active together, they will be drawn on top of eachother in the same order as they are in the sidebar.
{.is-info}
