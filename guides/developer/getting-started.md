---
title: Getting started with plugin development
description: An overview of the guides that'll teach you how to develop plugins for Artemis
published: true
date: 2026-01-10T13:09:31.150Z
tags: 
editor: markdown
dateCreated: 2025-10-12T16:21:02.621Z
---

# Introduction
This guide will help you get started developing plugins for Artemis. Before we get started you'll need a few things

- Basic knowledge of C# and .NET
- An IDE such as Visual Studio, Rider, or VS Code
    - The .NET 10 SDK (at the time of writing, this may change to a newer version)
- Artemis installed on your machine
- The Artemis Plugin Templates (we'll cover this in the next section)

If you don't know C# and/or .NET you can probably vibe code along, but it will be a lot harder. Consider learning the basics of C# and .NET first.

# Setting Up Your Development Environment
You'll need an IDE, I personally find [Rider](https://www.jetbrains.com/rider/) to be an excellent choice, not as heavy as Visual Studio but still very powerful. Visual Studio is also a great choice, especially if you're already familiar with it. VS Code can work too, but you'll need to set up some extensions to get a good experience.

Aside from an IDE it's recommended to use the Artemis Plugin Templates to get started quickly. These will set up a basic plugin structure for you.
You can find the templates on the Artemis GitHub repository or via NuGet.

To install the templates, run the following command:

```bash
dotnet new install ArtemisRGB.Templates
```

You can see all available templates by running

```bash
dotnet new list artemis
```

To update the templates, run the following command:

```bash
dotnet new update
```

> For full instructions check out the [Artemis Plugin Templates repository](https://github.com/Artemis-RGB/Artemis.Plugins.Templates).
{.is-info}

# Creating a new plugin
Once you have the templates installed, you can create a new plugin project.

## Using the Artemis.PluginTemplate repository template
We offer a repository template at https://github.com/Artemis-RGB/Artemis.PluginTemplate. You can use this to quickly create a new repo with a plugin solution in it.

## Manually creating a project
The templates allow you to either create an empty plugin, or create a plugin of a specific type (e.g. Module, Layer Brush, Device etc.).

It's up to you what you want to start with, but this guide will go with an empty plugin as an example. Separate guides are available for every plugin type.
As C# projects are typically organized in solutions, it's recommended to create a new solution for your plugin development, and place your plugin project inside that solution.  

You can do this in your IDE of choice or via the command line:

```bash
cd <your-desired-directory>
dotnet new sln
dotnet new artemis-plugin-empty -n Artemis.Plugins.ExamplePlugin
dotnet sln add Artemis.Plugins.ExamplePlugin/Artemis.Plugins.ExamplePlugin.csproj
```

This will create a new solution with an empty plugin project named `Artemis.Plugins.ExamplePlugin`. You can now open the solution in your IDE.
> You can also do this via your IDE's GUI if you prefer that, this example is simply IDE agnostic.
{.is-info}

# Understanding the Project Structure
Once you have created your plugin project, it's important to understand the project structure.
Here's a brief overview of the key files and folders:
- `Artemis.Plugins.ExamplePlugin.csproj`: This is the project file that contains information about your plugin, such as its dependencies and build settings.
    - `Bootstrapper.cs`: This is the main entry point for your plugin, it allows you to do some early setup if you need it. You can also remove it as it is optional.
    - `plugin.json`: This file contains metadata about your plugin, such as its name, version, etc. It also contains a unique identifier (GUID) for your plugin.
    
Some common use cases for the bootstrapper
- Adding plugin or feature prerequisites
- Registering a configuration dialog
- Registering dependency injection services with a custom scope (see [defining your own services](/guides/developer/getting-started#defining-your-own-services) below)

# Defining Plugin Metadata
The `plugin.json` file is where you define the metadata for your plugin. This includes information such as the plugin's name, version, author, and description.
For this tutorial we'll touch on the most common properties:
- `Name`: The name of your plugin as it will appear in Artemis.
- `Description`: A brief description of what your plugin does.
- `Author`: Your name!
- `Icon`: A material icon name to represent your plugin in the UI. You can find a list of available icons [here](https://materialdesignicons.com/).
- `Version`: The version of your plugin.
- `Website`: (Optional) A link to your website or the plugin's page.
- `Repository`: (Optional) A link to the source code repository for your plugin.

For the full list check out the definition of [`PluginInfo`](https://docs.artemis-rgb.com/api/Artemis.Core.PluginInfo.html?q=PluginInfo#properties) on our API docs.

# Adding a feature
Without any features, your plugin won't do much. Artemis plugins can have one or more features and can be toggled on or off individually. Features are where the actual functionality of your plugin lives.
To add a feature to your plugin, you can create a new class that inherits from [`PluginFeature`](https://docs.artemis-rgb.com/api/Artemis.Core.PluginFeature.html?q=pluginfeature), or one of it's derived types depending on what kind of feature you want to create.

A very straightforward plugin feature may look like this
```csharp
using System.Linq;
using Artemis.Core;
using Artemis.Core.Services;
using Serilog;

namespace Artemis.Plugins.ExamplePlugin;

[PluginFeature(Name = "My Amazing Feature", Description = "Some extra info on my feature")]
public class MyFeature : PluginFeature
{
    private readonly ILogger _logger;
    private readonly IProfileService _profileService;

    public MyFeature(ILogger logger, IProfileService profileService)
    {
        _logger = logger;
        _profileService = profileService;
    }

    public override void Enable()
    {
        _logger.Information("Hello world from MyFeature!");
        _logger.Information("It looks like you have {ProfileCount} profiles.", _profileService.ProfileCategories.SelectMany(c => c.ProfileConfigurations).Count());
    }

    public override void Disable()
    {
        _logger.Information("Goodbye world from MyFeature!");
    }
}
```

This feature simply logs a message when it is enabled and disabled, and also logs the number of profiles in the Artemis installation when enabled.

### Some notes on plugin features
- The [`[PluginFeature]`](https://docs.artemis-rgb.com/api/Artemis.Core.PluginFeatureAttribute.html#properties) attribute is optionally used to define metadata for the feature, such as its name and description.
    - A feature may be marked as always enabled using the `AlwaysEnabled` property of the attribute.
    - Plugins with a single feature always have that feature marked as always enabled.
- The constructor can take dependencies that will be injected by Artemis, such as the `ILogger` and [`IProfileService`](https://docs.artemis-rgb.com/api/Artemis.Core.Services.IProfileService.html?q=IProfileService) in this example.

# Dependency Injection
In the example above you may have noticed that the `MyFeature` class has a constructor that takes an `ILogger` and an [`IProfileService`](https://docs.artemis-rgb.com/api/Artemis.Core.Services.IProfileService.html?q=IProfileService). This is an example of dependency injection, a design pattern that allows you to decouple your code from its dependencies.

Dependency Injection is available in almost all classes that are instantiated by Artemis such as:
- Plugin Features (and all their subtypes such as Modules, Layer Effects, Device Providers, etc)
- Self-defined services (see below)
- View Models

## Defining your own Services
You can define your own services that can be injected into your plugin features and other classes.
To do this, create a class that implements the [`IPluginService`](https://docs.artemis-rgb.com/api/Artemis.Core.Services.IPluginService.html?q=IPluginService) interface.  Any service implementing this interface will be available inside the plugin as a singleton through dependency injection.

Alternatively, you can also opt to not implement [`IPluginService`](https://docs.artemis-rgb.com/api/Artemis.Core.Services.IPluginService.html?q=IPluginService) and manually call [`plugin.Register`](https://docs.artemis-rgb.com/api/Artemis.Core.Plugin.html?q=Plugin#Artemis_Core_Plugin_Register__1_Artemis_Core_PluginServiceScope_) in your bootstrapper's [`OnPluginEnabled`](https://docs.artemis-rgb.com/api/Artemis.Core.PluginBootstrapper.html?q=OnPluginEnabled#Artemis_Core_PluginBootstrapper_OnPluginDisabled_Artemis_Core_Plugin_). This allows you to use different [scopes](https://docs.artemis-rgb.com/api/Artemis.Core.PluginServiceScope.html).

If your service implements [`IDisposable`](https://learn.microsoft.com/en-us/dotnet/api/system.idisposable), Artemis will take care of disposing it when the plugin is unloaded.

## Built-in Services
Aside from defining your own services you can inject many of Artemis's own services into your plugin features and other classes. A full list of available services can be found in the API documentation:
- https://docs.artemis-rgb.com/api/Artemis.Core.Services.html?q=Services#interfaces
- https://docs.artemis-rgb.com/api/Artemis.UI.Shared.Services.html?q=Services#interfaces

# Building and Testing Your Plugin
Once you've added some features to your plugin, you'll want to build and test it. You can build your plugin using your IDE's build functionality or via the command line:
```bash
dotnet build -p:EnablePluginCopy=true
```

If you build inside Rider or Visual Studio, the plugin will automatically be copied to the Artemis plugins folder after a successful build. If you build via the command line, make sure to include the `-p:EnablePluginCopy=true` parameter to enable this behavior.  

After building your plugin, you can test it by launching Artemis (you can simply run the project from your IDE and it'll start Artemis). Your plugin should appear in the Plugins section of the Artemis settings. You can enable and disable your plugin and its features from there.

> The copying is done by the `ArtemisRGB.Plugins.BuildTask` NuGet package, which is included in the plugin templates by default.  
> The path that is copied to is `C:\ProgramData\Artemis\Plugins`.
{.is-info}

## Debugging
To debug your plugin, you can attach your IDE's debugger to the Artemis process. This allows you to set breakpoints and step through your code as it runs inside Artemis.  
The plugin templates include a launch configuration for both Rider and Visual Studio that will start Artemis with the debugger attached when you run the project. Alternatively you can manually attach the debugger to the Artemis process after starting it.

## Hot reloading
Artemis supports hot reloading of plugins, meaning you can make changes to your plugin code, rebuild it, and see the changes take effect without restarting Artemis.
To hot reload your plugin, simply rebuild it and Artemis will automatically unload the old version and load the new version.

This doesn't work well with a debugger attached, so it's recommended to only use hot reloading when not debugging.

## Viewing log messages
As our example feature logs messages when enabled and disabled, you'll want to be able to see those messages. Artemis uses [Serilog](https://serilog.net/) for logging, and log messages can be viewed in the Artemis debugger.
To open the debugger click on the debug icon in the top-right corner of the Artemis window, or go to `Settings > General > Tools > Show Debugger`.

Once open click on the logs tab to view log messages.

If we now enable and disable our example feature, we should see the log messages appear in the debugger.

```
[2026-01-09 22:47:04.591] [INF] [Artemis.Plugins.ExamplePlugin.MyFeature] Hello world from MyFeature!
[2026-01-09 22:47:04.591] [INF] [Artemis.Plugins.ExamplePlugin.MyFeature] It looks like you have 4 profiles.
```
And after disabling the feature:
```
[2026-01-09 22:48:14.367] [INF] [Artemis.Plugins.ExamplePlugin.MyFeature] Goodbye world from MyFeature!
```