---
title: Channels
description: A guide on Artemis update channels
published: true
date: 2023-03-03T12:30:07.307Z
tags: 
editor: markdown
dateCreated: 2023-03-03T12:26:53.678Z
---

# Introduction
Channels are a way for us to give users different versions of Artemis for testing purposes.  
Generally we recommend that you always stick to the **master** channel. That way you get the most stable version of the software.

Any other channels might be added/removed at any time, moving to a channel other than master could mean that you stop receiving updates.

> Updates on other channels may also not yet contain database migrations, meaning they can break your data.
{.is-danger}

## Changing to a different channel
If you still want to change channels it is possible to do so through a [startup argument](/startup-arguments).  

The channel can be set by providing `--channel={channel name}` e.g. `--channel=feature/amazing-stuff`
Removing the startup argument moves you back to the master channel.