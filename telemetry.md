---
title: Telemetry in Artemis
description: A page detailing the telemetry Artemis gathers
published: true
date: 2021-07-05T12:47:24.515Z
tags: 
editor: markdown
dateCreated: 2021-07-05T10:58:31.609Z
---

> Telemetry is not currently included, this page is a draft
{.is-warning}


# Overview
Since build `xxxxx` Artemis will gather small amounts of anonymous telemetry using [Matomo](https://matomo.org/) to help me improve the application.

This is enabled by default but during the initial configuration wizard you are offered the option to disable it. You can also always disable telemetry in the **General** tab of the **Settings** page.

## What is being gathered
If telemetry is enabled Artemis gatheres the following information
- OS version
- Application initialize
- Page views
- Update accept/decline
- Fatal exceptions

## Why it's gathered
The things above are gathered to give me an idea of what people use Artemis for. 

The OS version will tell me if I should care about supporting older versions of Windows. 
Application initialize tells me how many people use Artemis in the first place. 
The page views let me know which parts of the UI are used frequently and which parts are not, allowing me to focus on the popular parts.
Update accept/decline will let me know if people are deliberately sticking to an older version.
Fatal exceptions will help me track down issues.

## How data is stored and for how long it's kept
Data is anonymously stored on the Artemis server for 90 days.