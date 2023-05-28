---
title: Scripting
description: A guide on how to use scripts to customize Artemis profiles
published: true
date: 2021-06-29T15:39:52.267Z
tags: 
editor: markdown
dateCreated: 2021-06-19T12:56:42.863Z
---

> This guide assumes you are using the default JavaScript scripting provider.
{.is-info}

# Introduction
While Artemis offers loads of customizability via it's UI, there will always be limits to what you can do.
To help overcome some of these limits without the need of an entire plugin, you can choose to write a script.

By default Artemis ships with a [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) scripting provider. This provider uses the [JINT JavaScript engine](https://github.com/sebastienros/jint) providing almost full EcmaScript 2020 support.

## Script types
There are several types of scripts available. The type determines when the script is active and what info is available to the script.

The main difference between the different types is the 'scope' in which the script runs. 
The upside of using a layer script over a profile script is that you do not need to worry about retrieving the layer yourself. 
A layer script is configured for **one layer** and only has control over that layer. The same applies to layer property scripts, it is simply a way to help separate and simplify scripts.

### Global
The most broad scope being a [global script](/guides/user/profiles/scripting/global-script) which can be used to run scripts whenever Artemis is active.

**Example usage of a global script might be be**
- Adding extra data to the data model without creating an entire module
- Activating profiles with custom logic

### Profile
The next type is a [profile script](/guides/user/profiles/scripting/profile-script), these kinds of scripts run within the scope of a profile and are only active while the profile is active.

**Example usage of a profile script might be be**
- Controlling the activation conditions of multiple layers
- Modifying the properties of multiple layers
- Drawing custom shapes/text on top of the profile using the full SkiaSharp API

### Layer
The next type is a [layer script](/guides/user/profiles/scripting/layer-script), these kinds of scripts run within the scope of a layer and are only active while the profile containing the layer is active.

**Example usage of a layer script might be be**
- Controlling the activation conditions of a specific layer
- Modifying the properties of a specific layer
- Drawing custom shapes/text on top of the layer using the full SkiaSharp API

### Layer property
The next type is a [layer property script](/guides/user/profiles/scripting/layer-property-script), these kinds of scripts run within the scope of a single layer property and are only active while the profile containing the layer is active.

**Example usage of a layer script might be be**
- Creating custom data bindings for a property
