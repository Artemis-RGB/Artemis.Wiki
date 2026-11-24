---
title: Local REST API
description: An overview of the local REST API offered by Artemis
published: true
date: 2025-10-13T08:50:12.366Z
tags: 
editor: markdown
dateCreated: 2025-10-12T16:21:08.169Z
---

# Introduction
Artemis runs a local web server that can be used to externally (but on the local system) interact with the application.
Out of the box this API offers remote control, access to the data model and more. The API may also be expanded by plugins with new end points.

# Getting started
In order to access the API you need to find out on which port the API is listening. 
Artemis stores the full API URL including the current port in a text file found in `%ProgramData%/Artemis/webserver.txt`
A sample value: `http://localhost:9696/`

> By default the API can only be accessed locally, remote access can be enabled in Settings > General > Web server > Remote access.
{.is-warning}


# Built-in APIs
Except for the remote control API, these are all provided by the Artemis Web API plugin.
The APIs provided by the plugin are implemented as separate plugin features which means they can be disabled.

## Remote control
THe remote control API provides limited control over the application via POST calls.
| Method | Endpoint                     | Description                      | Body                                              | Body Type    |
| ------ | ---------------------------- | -------------------------------- | ------------------------------------------------- | ------------ |
| POST   | `remote/bring-to-foreground` | Brings Artemis to the foreground | An optional route to view                         | string       |
| POST   | `remote/restart`             | Restarts Artemis                 | The command line args to pass to the new instance | string array |
| POST   | `remote/shutdown`            | Shuts down Artemis               | -                                                 | -            |

## Plugins
The plugins API allows you to view and call plugin endpoints. It can be used to push external state to your plugin.
| Method | Endpoint                                | Description                        |
| ------ | --------------------------------------- | ---------------------------------- |
| GET    | `plugins/endpoints`                     | List all the available endpoints   |
| GET    | `plugins/endpoints/{plugin}/{endPoint}` | List the properties of an endpoint |

## Profiles
The profiles API allows control over profile states
| Method | Endpoint                       | Description                                   | Body                         | Body Type             |
| ------ | ------------------------------ | --------------------------------------------- | ---------------------------- | --------------------- |
| GET    | `profiles`                     | List all profiles of the user                 | -                            | -                     |
| GET    | `profiles/categories`          | List all the categories of the user           | -                            | -                     |
| POST   | `profiles/suspend/{profileId}` | Toggles suspension of the provided profile ID | `suspend`: `true` or `false` | x-www-form-urlencoded |

## Data model
The data model API allows you to read the data model 
| Method | Endpoint     | Description                |
| ------ | ------------ | -------------------------- |
| GET    | `data-model` | Gets the entire data model |

> Dynamic data models are not yet supported
> {.is-info}

## JSON modules
The JSON modules API allows you to create Artemis modules without the need of a plugin.  
Simply POSTing a [JSON schema](https://json-schema.org/) to this endpoint creates a new module in Artemis. You can than POST JSON to that module to update it, making external data available in the data model.

Learn more on the [dedicated JSON modules page](/guides/developer/json-modules).

| Method | Endpoint                         | Description                                                   | Body              | Body Type |
| ------ | -------------------------------- | ----------------------------------------------------------    | ----------------- | --------- |
| GET    | `json-modules`                   | Gets all registered JSON modules and their schema             | -                 | -         |
| POST   | `json-modules/{moduleId}/schema` | Updates or registers a new module with the provided module ID | The JSON schema   | JSON      |
| POST   | `json-modules/{moduleId}/data`   | Applies the provided JSON to the module matching module ID    | The data to apply | JSON      |



> Make sure you pick a unique module ID but don't change it later, the ID will get stored in profiles that point to your JSON module.
> {.is-info}

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