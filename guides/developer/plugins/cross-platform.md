---
title: Creating Cross Platform Plugins
description: A guide on how to create platform-specific services for your features
published: true
date: 2022-07-26T07:28:59.675Z
tags: 
editor: markdown
dateCreated: 2022-07-26T06:55:48.501Z
---

# Introduction
Since Artemis has been ported to Avalonia cross-platform support has been added for Windows, Linux and OSX.

This also has impact on plugin developers, mainly since due to their nature plugins usually won't be able to support each platform.
An example could be a device provider using a Windows-SDK, a module reading Windows performance counters etc. etc.

On this page you'll find what you can do to provide a smooth experience across one or more platforms of your choice.

> If you are not using any native OS APIs or interacting with other software that is tied to a single platform, always try to support all platforms. Only limit your support once you run into limitations.
{.is-info}


# Limiting your plugin to one or more platforms
To ensure both the .NET SDK and Artemis know your plugin won't run on every platform you need to perform a few steps
## .NET
The first thing to do is tell the .NET SDK what your target(s) are.
Open your `.csproj` file and find the `<TargetFramework>` property. Limit it to one or more OSes like so:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net6.0-windows</TargetFramework>
    <Platforms>x64</Platforms>
    <EnableDynamicLoading>true</EnableDynamicLoading>
    <ProduceReferenceAssembly>false</ProduceReferenceAssembly>
  </PropertyGroup>
  ...
```
If you want to support multiple platforms, use `;` to separate values, to support all platforms simply target `net6.0`. Other relevant values are `net6.0-windows` and `net6.0-macos`. There is no separate value for Linux, simply use `net6.0`. [Microsoft documentation](https://docs.microsoft.com/en-us/dotnet/standard/frameworks#net-5-os-specific-tfms) 

## plugin.json
The next step is to inform Artemis under which platforms your plugin can load.
Open your `.plugin.json` and add the `Platforms` property like so:
```json
{
  ...
  "Main": "MyCrossPlatformPlugin.dll",  
  "Platforms":"Windows, Linux"
}
```
Use `,` to separate values, to support all platforms simply exclude the property. Possible values are `Linux`, `Windows`, `OSX`.

# Creating platform specific services
Usually plugin services will implement [IPluginService](https://artemis-rgb.com/docs/api/Artemis.Core.Services.IPluginService.html?q=IPluginService) which will automatically register them as [singletons](https://en.wikipedia.org/wiki/Singleton_pattern). However, we now want control over the registration of our service and so we implement our own interface and register it manually

```cs
public interface IMyPluginService
{
    void SayHi();
}
```

We'll then provide a Windows and a Linux implementation of this interface
```cs
[SupportedOSPlatform("windows")]
public class MyWindowsPluginService : IMyPluginService
{
    private readonly ILogger _logger;

    public MyWindowsPluginService(ILogger logger)
    {
        _logger = logger;
    }
    public void SayHi()
    {
        _logger.Information("Hi from Windows :)");
    }
}

[SupportedOSPlatform("linux")]
public class MyLinuxPluginService : IMyPluginService
{
    private readonly ILogger _logger;

    public MyLinuxPluginService(ILogger logger)
    {
        _logger = logger;
    }
    public void SayHi()
    {
        _logger.Information("Hi from Linux :)");
    }
}
```
The `SupportedOSPlatform` attribute has nothing to do with Artemis and is optional but tells the compiler it's safe to call OS-specific code in your service. [You can learn more about it here](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/quality-rules/ca1416).

Finally in your plugins bootstrapper, register the correct service
```cs
public class Bootstrapper : PluginBootstrapper
{
    public override void OnPluginEnabled(Plugin plugin)
    {
        if (OperatingSystem.IsWindows())
            plugin.Kernel!.Bind<IMyPluginService>().To<MyWindowsPluginService>().InSingletonScope();
        else if (OperatingSystem.IsLinux())
            plugin.Kernel!.Bind<IMyPluginService>().To<MyLinuxPluginService>().InSingletonScope();
    }
}
```
> To do this you need to reference Ninject as a Nuget package, make sure you somewhat match the version of Artemis.
{.is-info}
