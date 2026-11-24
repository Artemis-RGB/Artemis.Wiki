---
title: JSON modules
description: Adding modules to Artemis without a plugin
published: true
date: 2025-10-13T08:50:09.014Z
tags: 
editor: markdown
dateCreated: 2025-10-13T08:49:02.407Z
---

# JSON modules
The JSON modules API allows you to create Artemis modules without the need of a plugin.  
Simply POSTing a [JSON schema](https://json-schema.org/) to this endpoint creates a new module in Artemis. You can than PUT JSON to that module to update it, making external data available in the data model and [data model nodes](/guides/user/profiles/nodes/datamodel).

> JSON modules do not support arrays of objects, only arrays of primitive types. If you do wish to use these, consider writing a full plugin.
{.is-warning}

## A quick summary of what you should do to use this

1. Predetermine a module ID that is unique and won't change
1. Send a JSON schema to `json-modules/{moduleId}/schema`
2. Send data updates as JSON to `json-modules/{moduleId}/data`

It is safe to send the same schema multiple times but it's best to always send the schema **once** before sending data. Once you've sent the schema you can send data as often as you like, though more than 25 times per second is probably pointless since Artemis by default runs at 25 fps.

# Registering and using a new module
There are a few steps to providing your JSON module to Artemis, we'll walk you through them here.
In this example we'll add a JSON module that provides the following data to Artemis

```json
{
  "player": {
    "name": "DragonSlayer99",
    "health": 85,
    "maxHealth": 100,
    "score": 12500,
    "level": 7,
    "weapon": {
      "name": "Iron Sword",
      "damage": 15,
      "durability": 80,
      "maxDurability": 100
    }
  },
  "world": {
    "location": "Dark Forest",
    "timeElapsed": 3600.00
  }
}
```

## Create a module ID
To register a new module, come up with a unique ID for it, it should be 50 characters or less and preferably something that won't clash with someone else's, so include your project's name plus a hash or something similar.

Some good examples
* `my-json-module-251f7sa`
* `firefox-integration-gd8201f`

## Create or generate a JSON schema
Once you have an ID, you can register your module with Artemis.  
To do so, Artemis expects something called a JSON schema. A JSON Schema is a blueprint for structuring JSON data. It defines the expected format, data types, required fields, and validation rules for JSON objects. 

For Artemis only the expected format and data types are relevant, the rest is ignored. 

There are multiple ways to get a JSON schema, depending on what language or framework you're using to send the JSON, you may be able to generate a schema in code.  
Alternatively you can use an online tool like https://www.liquid-technologies.com/online-json-to-schema-converter to create a schema based on a sample JSON payload, that's what we did for this guide.
```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "object",
  "properties": {
    "player": {
      "type": "object",
      "properties": {
        "name": {
          "type": "string"
        },
        "health": {
          "type": "integer"
        },
        "maxHealth": {
          "type": "integer"
        },
        "score": {
          "type": "integer"
        },
        "level": {
          "type": "integer"
        },
        "weapon": {
          "type": "object",
          "properties": {
            "name": {
              "type": "string"
            },
            "damage": {
              "type": "integer"
            },
            "durability": {
              "type": "integer"
            },
            "maxDurability": {
              "type": "integer"
            }
          },
          "required": [
            "name",
            "damage",
            "durability",
            "maxDurability"
          ]
        }
      },
      "required": [
        "name",
        "health",
        "maxHealth",
        "score",
        "level",
        "weapon"
      ]
    },
    "world": {
      "type": "object",
      "properties": {
        "location": {
          "type": "string"
        },
        "timeElapsed": {
          "type": "number"
        }
      },
      "required": [
        "location",
        "timeElapsed"
      ]
    }
  },
  "required": [
    "player",
    "world"
  ]
}
```

## Registering the module
Now with our schema ready we can register our module with Artemis. To do so we'll make a `POST` call to `http://localhost:9696/json-modules/{moduleId}/schema`.  
In our case it'll be `http://localhost:9696/json-modules/my-json-module-251f7sa/schema`. The body of the POST will be the JSON schema as shown above.

When we send our schema off Artemis own't accept it however, we'll get this error back:
```json
{
    "status": 500,
    "message": "JSON module schema must have a title"
}
```

JSON schema allows giving each property a `title` and `description` normally both are optional but Artemis requires the root object to have a title, since it'll be what's shown in the data model.  
We'll update our schema and include a title, we'll also give the `player name` property a title and description:
```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "title": "My amazing JSON module",
  "type": "object",
  "properties": {
    "player": {
      "type": "object",
      "properties": {
        "name": {          
          "title": "Player name",
          "description": "The name of the player",
          "type": "string"
        },
	 
        // ... the rest of the schema is omitted for brevity
}
```

Now when we send this off our module will be registered and available in the data model! We can see this in the debugger:
![schema in debugger](https://i.imgur.com/wEGqOv3.png){.elevation-3 .radius-3}

The title we gave our schema shows up here, as well as the custom title and description for the player name. For all the other properties we didn't provide a title or description, so the property names will simply be humanized and shown.

## Sending data
We can now send data to our JSON module, we'll send the JSON payload initially mentioned:

`POST` to `http://localhost:9696/json-modules/my-json-module-251f7sa/data`:
```json
{
  "player": {
    "name": "DragonSlayer99",
    "health": 85,
    "maxHealth": 100,
    "score": 12500,
    "level": 7,
    "weapon": {
      "name": "Iron Sword",
      "damage": 15,
      "durability": 80,
      "maxDurability": 100
    }
  },
  "world": {
    "location": "Dark Forest",
    "timeElapsed": 3600.00
  }
}
```

With the data sent off to Artemis, the data model will immediately update in the debugger:
![data in debugger](https://i.imgur.com/Cy1C1GQ.png){.elevation-3 .radius-3}

# Removing JSON modules
Currently it's only possible to remove all JSON modules at once. To do so navigate to **Settings** > **Plugins** and search for the **Artemis Web API** plugin. Click on **Manage** and finally **Clear plugin settings**.
![data in debugger](https://i.imgur.com/GbBP1s7.png){.elevation-3 .radius-3}

# API Overview
| Method | Endpoint                         | Description                                                   | Body              | Body Type |
| ------ | -------------------------------- | ----------------------------------------------------------    | ----------------- | --------- |
| GET    | `json-modules`                   | Gets all registered JSON modules and their schema             | -                 | -         |
| POST   | `json-modules/{moduleId}/schema` | Updates or registers a new module with the provided module ID | The JSON schema   | JSON      |
| POST   | `json-modules/{moduleId}/data`   | Applies the provided JSON to the module matching module ID    | The data to apply | JSON      |

