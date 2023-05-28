---
title: Local REST API
description: An overview of the local REST API offered by Artemis
published: true
date: 2021-06-24T08:05:41.981Z
tags: 
editor: markdown
dateCreated: 2021-01-29T19:34:25.219Z
---

# Introduction
Artemis runs a local web server that can be used to externally (but on the local system) interact with the application.
Out of the box this API offers remote control, access to the data model and more. The API may also be expanded by plugins with new end points.

# Getting started
In order to access the API you need to find out on which port the API is listening. 
Artemis stores the full API URL including the current port in a text file found in `%ProgramData%/Artemis/webserver.txt`
A sample value: `http://localhost:9696/`

> Without NAT the API can only be accessed from the same network, remote access is not possible.
{.is-warning}


# Built-in APIs
Except for the remote control API, these are all provided by the Artemis Web API plugin.
The APIs provided by the plugin are implemented as separate plugin features which means they can be disabled.
## Remote control
`POST` `remote/bring-to-foreground`
`POST` `remote/restart`
`POST` `remote/shutdown`
> These cannot be disabled as they are used by the UI to talk to duplicate instances of Artemis.
{.is-info}

## Plugins
`GET` `plugins/endpoints`
`GET` `plugins/endpoints/{plugin}/{endPoint}`

## Profiles
`GET` `profiles`
`GET` `profiles/categories`
`POST` `profiles/suspend/{profileId}` - include form data `suspend` `true` or `false`

## Data model
`GET` `data-model`
> Dynamic data models are not yet supported
{.is-info}


# Using plugin end points
You can get a list of all plugin end points by calling `plugins/endpoints`. 
The response contains an `Url` field which you can use to find out how to call the end point.
All calls to the **plugin** end point must be `POST` calls (with the exception of end points of type RawPluginEndPoint, they can be any type)

## Sample response
```json
[
    {
        "Name": "StringEndPoint",
        "Url": "http://localhost:9696/plugins/ab41d601-35e0-4a73-bf0b-94509b006ab0/StringEndPoint",
        "PluginInfo": {
            "Guid": "ab41d601-35e0-4a73-bf0b-94509b006ab0",
            "Name": "Test data model expansion",
            "Description": "A data model expansion providing test data",
            "Icon": "TestTube",
            "Version": "1.0.1.416",
            "Main": "Artemis.Plugins.DataModelExpansions.TestData.dll",
            "AutoEnableFeatures": true,
            "RequiresAdmin": false
        },
        "Accepts": "text/plain",
        "Returns": null
    },
    {
        "Name": "StringEndPointWithResponse",
        "Url": "http://localhost:9696/plugins/ab41d601-35e0-4a73-bf0b-94509b006ab0/StringEndPointWithResponse",
        "PluginInfo": {
            "Guid": "ab41d601-35e0-4a73-bf0b-94509b006ab0",
            "Name": "Test data model expansion",
            "Description": "A data model expansion providing test data",
            "Icon": "TestTube",
            "Version": "1.0.1.416",
            "Main": "Artemis.Plugins.DataModelExpansions.TestData.dll",
            "AutoEnableFeatures": true,
            "RequiresAdmin": false
        },
        "Accepts": "text/plain",
        "Returns": "text/plain"
    },
    {
        "ThrowOnFail": true,
        "Name": "JsonEndPoint",
        "Url": "http://localhost:9696/plugins/ab41d601-35e0-4a73-bf0b-94509b006ab0/JsonEndPoint",
        "PluginInfo": {
            "Guid": "ab41d601-35e0-4a73-bf0b-94509b006ab0",
            "Name": "Test data model expansion",
            "Description": "A data model expansion providing test data",
            "Icon": "TestTube",
            "Version": "1.0.1.416",
            "Main": "Artemis.Plugins.DataModelExpansions.TestData.dll",
            "AutoEnableFeatures": true,
            "RequiresAdmin": false
        },
        "Accepts": "application/json",
        "Returns": null
    },
    {
        "ThrowOnFail": true,
        "Name": "JsonEndPointWithResponse",
        "Url": "http://localhost:9696/plugins/ab41d601-35e0-4a73-bf0b-94509b006ab0/JsonEndPointWithResponse",
        "PluginInfo": {
            "Guid": "ab41d601-35e0-4a73-bf0b-94509b006ab0",
            "Name": "Test data model expansion",
            "Description": "A data model expansion providing test data",
            "Icon": "TestTube",
            "Version": "1.0.1.416",
            "Main": "Artemis.Plugins.DataModelExpansions.TestData.dll",
            "AutoEnableFeatures": true,
            "RequiresAdmin": false
        },
        "Accepts": "application/json",
        "Returns": "application/json"
    }
]
```