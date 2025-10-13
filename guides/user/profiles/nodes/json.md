---
title: JSON node
description: The help page of the JSON Node
published: true
date: 2024-02-28T20:15:36.720Z
tags: 
editor: markdown
dateCreated: 2024-02-25T11:17:41.229Z
---

# Introduction
The JSON node is an advanced node provided by the [Advanced Text Nodes](https://workshop.artemis-rgb.com/entries/204/advanced-text-nodes) plugin. It allows querying JSON using a syntax known as a [JSON Path](https://goessner.net/articles/JsonPath/).

[![img](https://workshop.artemis-rgb.com/entries/204/banner.png  =600x)](https://workshop.artemis-rgb.com/entries/204/advanced-text-nodes){.radius-3}

# Examples
In this first example we use a path `$.Manufacturers[1].Products[1].Name` to get the name of the second product of the second manufacturer.

![img](https://i.imgur.com/NabmRdu.png){.elevation-3 .radius-3}

In this first example we use a path `$.Manufacturers[1].Products[1].Price` to get the price instead, note how the output of the node changed from <i class="v-icon mdi mdi-circle" style="color: #FFD700"></i> text to <i class="v-icon mdi mdi-circle" style="color: #32CD32"></i> number.
![img](https://i.imgur.com/sun9wYM.png){.elevation-3 .radius-3}


# Getting a JSON path
If you don't want to get into the JSON path syntax and all its wonders, this website allows you to quickly get a JSON path from a sample JSON input: https://www.site24x7.com/tools/jsonpath-finder-validator.html

>Starting with `$.` is part of the standard, the website above doesn't include it so you'll need to add it yourself.

# JSON.NET JsonPath Syntax Cheatsheet

JsonPath is a query language for JSON data structures, allowing you to extract and manipulate data from JSON documents.

## Basic Syntax:

- `$`: Represents the root object.
- `.`: Dot notation for accessing properties.
- `['property']`: Bracket notation for accessing properties with special characters or spaces.

## Examples:

Given the following JSON structure:

```json
{
  "name": "John",
  "age": 30,
  "address": {
    "city": "New York",
    "zip": "10001"
  },
  "emails": ["john@example.com", "john.doe@example.com"]
}
```
### Path Expressions:

- `$.name`: Selects the value of the `name` property.
- `$.address.city`: Selects the value of the `city` property within the `address` object.
- `$.emails[0]`: Selects the first email address.
- `$.emails[*]`: Selects all email addresses.
- `$..name`: Recursively selects all values named `name`.

### Filter Expressions:

- `$..emails[?(@.length() > 15)]`: Selects emails with a length greater than 15 characters.

### Functions:

- `length()`: Returns the length of an array or string.
- `size()`: Returns the number of child elements of an object.

### Wildcards:

- `*`: Matches any property name or array index.

### Union:

- `$.name | $.age`: Returns the `name` and `age` properties.

### Descendants:

- `$..*`: Recursively selects all members of an object or array.

## Conclusion (as provided by ChatGPT, lol):

JsonPath provides a concise and powerful way to navigate and query JSON data structures. Use it to extract and manipulate data efficiently.