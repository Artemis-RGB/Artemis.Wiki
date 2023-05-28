---
title: Remote Control Brush
description: A guide on how to use the web API offered by the remote control brush
published: true
date: 2021-06-24T07:51:34.242Z
tags: 
editor: markdown
dateCreated: 2021-06-16T21:03:44.293Z
---

# Introduction
The remote control brush allows you to remotely set the color of LEDs. This is achieved by applying the **Remote Control** brush to a layer. The LEDs of this layer can then be remotely controlled.

# Getting started
In order to access the API you need to find out on which port the API is listening. 
Artemis stores the full API URL including the current port in a text file found in `%ProgramData%/Artemis/webserver.txt`
A sample value: `http://localhost:9696/`

> Without NAT the API can only be accessed from the same network, remote access is not possible.
{.is-warning}

# API
## Retrieving active brushes
You can get a list of all currently active remote control brushes
`GET` `http://{url}/remote-control-brushes`

A response might look like this
```json
[
    {
        "$id": "1",
        "ProfileId": "e3cad4e0-2b10-4644-8f7a-ee1ed11f1490",
        "ProfileName": "My amazing profile",
        "LayerId": "4896ee13-4c1b-4462-bf4b-78d0fb30472d",
        "LayerName": "New layer"
    },
    {
        "$id": "2",
        "ProfileId": "67594022-586b-4edc-8e26-ae19fc072149",
        "ProfileName": "Another amazing profile",
        "LayerId": "d70883c3-3712-47af-a69c-7f1ce857d39f",
        "LayerName": "New layer"
    }
]
```  

## Retrieving colors 
You can get the colors on a per-brush basis by providing the brush ID
`GET` `http://{url}/remote-control-brushes/{brushId}`

A response might look like this
```json
{
    "$id": "1",
    "ProfileId": "67594022-586b-4edc-8e26-ae19fc072149",
    "ProfileName": "Another amazing profile",
    "LayerId": "d70883c3-3712-47af-a69c-7f1ce857d39f",
    "LayerName": "New layer",
    "LedColors": [
        {
            "$id": "2",
            "LedId": "Keyboard_1",
            "Color": "#00000000"
        },
        {
            "$id": "3",
            "LedId": "Keyboard_2",
            "Color": "#00000000"
        },
        {
            "$id": "4",
            "LedId": "Keyboard_3",
            "Color": "#00000000"
        },
        {
            "$id": "5",
            "LedId": "Keyboard_4",
            "Color": "#00000000"
        },
        {
            "$id": "6",
            "LedId": "Keyboard_5",
            "Color": "#00000000"
        },
        {
            "$id": "7",
            "LedId": "Keyboard_6",
            "Color": "#00000000"
        },
        {
            "$id": "8",
            "LedId": "Keyboard_7",
            "Color": "#00000000"
        },
        {
            "$id": "9",
            "LedId": "Keyboard_8",
            "Color": "#00000000"
        },
        {
            "$id": "10",
            "LedId": "Keyboard_9",
            "Color": "#00000000"
        },
        {
            "$id": "11",
            "LedId": "Keyboard_0",
            "Color": "#00000000"
        }
    ]
}
```  

## Setting colors
You can set colors by providing a JSON array of **LedColors**
`POST` `http://{url}//remote-control-brushes/{brushId}/update-colors`

A request might look like this
```json
[
    {
        "LedId": "Keyboard_1",
        "Color": "#FFFF0055"
    },
    {
        "LedId": "Keyboard_2",
        "Color": "#FFFF0055"
    },
    {
        "LedId": "Keyboard_3",
        "Color": "#FFFF0055"
    },
    {
        "LedId": "Keyboard_4",
        "Color": "#FF00FF00"
    },
    {
        "LedId": "Keyboard_5",
        "Color": "#FF00FF00"
    },
    {
        "LedId": "Keyboard_6",
        "Color": "#FF00FF00"
    },
    {
        "LedId": "Keyboard_7",
        "Color": "#00000000"
    },
    {
        "LedId": "Keyboard_8",
        "Color": "#00000000"
    },
    {
        "LedId": "Keyboard_9",
        "Color": "#00000000"
    },
    {
        "LedId": "Keyboard_0",
        "Color": "#00000000"
    }
]
```  
### Notes
- Colors are in HEX either `#AARRGGBB` or `#RRGGBB`
- Any omitted LEDs will keep their current color