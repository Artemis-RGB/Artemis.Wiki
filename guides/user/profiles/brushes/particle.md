---
title: Particle Brush
description: A guide explaining how to get the most out of the particle brush
published: true
date: 2021-03-31T10:57:20.373Z
tags: 
editor: markdown
dateCreated: 2021-03-31T10:40:29.227Z
---

# Custom path
When using a custom path particle, you have to provide your own SVG path.

## Creating your own path
If you want to create your own path there are plenty of options. On Google you can find many different editors such as this one https://yqnn.github.io/svg-path-editor/

## Using .svg files

You can also use any SVG off the internet, per example this flame:  
![flame](https://upload.wikimedia.org/wikipedia/commons/d/dc/Flame.svg)
*Source: https://commons.wikimedia.org/wiki/File:Flame.svg*

To use this file save it somewhere and open it with a text editor. You'll see something like this:
```svg
<?xml version="1.0" encoding="utf-8"?>
<!-- Generator: Adobe Illustrator 16.0.0, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg version="1.1" id="Camada_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 width="308px" height="534px" viewBox="151.5 50.5 308 534" enable-background="new 151.5 50.5 308 534" xml:space="preserve">
<path d="M430.095,366.991c-32.803-42.283-33.434-90.521-16.298-133.116c-36.315,35.569-56.763,79.548-42.484,123.955
	c1.812,5.648,2.974,11.181,3.824,16.83l0.325,6.812l-2.026,0.746l-8.623-19.706c-12.252-33.538-14.058-68.899-2.025-105.215
	c23.96-71.133-7.344-140.785-64.426-196.795c26.304,67.724,23.856,144.726-29.388,212.884c-10.227,12.993-18.636,26.2-25.343,39.719
	l-4.052,8.941l0.324-2.338c10.753-45.789-12.674-87.326-51.652-118.63c20.232,40.569,23.323,88.71-6.071,134.499
	c-24.603,47.277-30.888,105.962-11.609,149.519c30.141,62.938,70.185,91.903,124.604,93.391c7.876,0.104,15.973-0.208,24.283-1.278
	c44.407-4.792,99.891-26.506,117.779-77.944C454.911,455.162,463.326,410.003,430.095,366.991z"/>
</svg>
```

The interesting part for us is in the `<path>` tag and more importantly everything between the double quotes in `d=""`.
```
M430.095,366.991c-32.803-42.283-33.434-90.521-16.298-133.116c-36.315,35.569-56.763,79.548-42.484,123.955
  c1.812,5.648,2.974,11.181,3.824,16.83l0.325,6.812l-2.026,0.746l-8.623-19.706c-12.252-33.538-14.058-68.899-2.025-105.215
  c23.96-71.133-7.344-140.785-64.426-196.795c26.304,67.724,23.856,144.726-29.388,212.884c-10.227,12.993-18.636,26.2-25.343,39.719
  l-4.052,8.941l0.324-2.338c10.753-45.789-12.674-87.326-51.652-118.63c20.232,40.569,23.323,88.71-6.071,134.499
  c-24.603,47.277-30.888,105.962-11.609,149.519c30.141,62.938,70.185,91.903,124.604,93.391c7.876,0.104,15.973-0.208,24.283-1.278
  c44.407-4.792,99.891-26.506,117.779-77.944C454.911,455.162,463.326,410.003,430.095,366.991z
```

When you copy the entire path and paste it into the input field in Artemis, it'll work! 
> Some SVGs use multiple paths, in that case just copy them all one by one and paste with a whitespace between them.
{.is-info}

## Using Material Design icons
You can use any icon from https://materialdesignicons.com/ since they are available in SVG format.
Once you've found a nice icon click on the <i class="v-icon mdi mdi-xml"></i>-button and select **View SVG** from there the process is the same as when using an SVG file.

![particle-brush-material.png](/guides/user/profiles/brushes/particle-brush-material.png){.elevation-3 .radius-3}
