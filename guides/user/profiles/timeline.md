---
title: Timeline
description: This guide will explain how the timeline works during playback and while using the profile editor.
published: true
date: 2021-01-14T09:16:55.820Z
tags: 
editor: markdown
dateCreated: 2020-12-22T09:10:24.858Z
---

**Looking for something more specific?**
- [Keyframes](/guides/user/profiles/timeline/keyframes) - This guide shows you what keyframes are and how you can use them to create all kinds of animations.
- [Segments](/guides/user/profiles/timeline/segments) - This guide will explain how you can split the timeline of a layer up in separate parts for advanced usage in combination with conditions.

Alternatively, head back to the guide overview on the [getting started](/guides/user) page.

# Introduction
The main purpose of the timeline is to create custom animations using <i class="v-icon mdi mdi-timer"></i> keyframes. 
Timelines are a more advanced topic but for simple animations using the default brushes you generally don't need to use one.

**There are a few bullet points that are important to remember getting in to timelines**
- Each layer has its own timeline, there is no shared timeline.
- Timelines may stop/start at different times depending on conditions.
- Timelines can repeat, depending on how they are configured.

The timeline allows you to change the value of one or more properties over time. The way this is done is by giving a property multiple values at different points in time, these values are called keyframes. When the timeline plays Artemis smoothly follows these keyframes, resulting in an animation.

The timeline is split up into separate rails. **Each property has its own rail** and on these rails you can place keyframes. Because of this, you'll be using the properties panel and the timelines panel together a lot.

![timeline.png](/guides/user/profiles/timeline.png){.elevation-3 .radius-3}
In the image above you'll see that keyframes are enabled for the **Position**, **Scale** and **Rotation** properties. This was achieved by clicking the <i class="v-icon mdi mdi-timer"></i>-icon in front of each property.

After enabling keyframes, a new keyframe is added right away. Each keyframe is shown on the timeline using circle like this one: <i class="v-icon mdi mdi-checkbox-blank-circle" style="color: #009688"></i>. 
You can drag these around to change their position. The position of your keyframes the **start**, **end** and **speed** of the animation.

Changing the value of a property which has keyframes enabled adds a new keyframe at the current position of the timeline cursor. 

Collapsing a property will also collapse the rails, causing all keyframes to be consolidated into a single rail which you cannot edit.
![timeline-collapsed.png](/guides/user/profiles/timeline-collapsed.png){.elevation-3 .radius-3}

To learn about the timeline and keyframes, see the [timeline guide](/guides/user/profiles/timeline) and more specifically the [keyframes guide](/guides/user/profiles/timeline/keyframes).