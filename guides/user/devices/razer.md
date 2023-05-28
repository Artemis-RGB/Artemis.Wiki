---
title: Razer
description: An overview of the Razer support provided by the default Artemis Razer plugin
published: true
date: 2021-06-17T20:15:16.319Z
tags: device, razer
editor: markdown
dateCreated: 2021-01-25T15:16:31.741Z
---

# Introduction
![razer-logo.png](/vendors/razer-logo.png){.align-abstopright}Artemis supports Razer Chroma products through the official Razer Chroma SDK.

# Requirements
For Razer support you need [Razer Synapse](https://www.razer.com/synapse-3). 
If you already have Synapse installed, make sure it is up-to-date and Artemis will run out of the box.

# Troubleshooting
If your device is supported by the SDK but does not show up in Artemis, it means we need its `PID` in order to identify it.

Getting the PID is easy, The Razer plugin logs the ones it finds for you.
You'll find your log files in the `logs` directory next to the Artemis application folder (`%ProgramData%\Artemis\logs`) or under **Settings** > **Show Logs**.

Once you've found your log either create an issue [here](https://github.com/Artemis-RGB/Artemis.Plugins/issues) and include your logs (GitHub account required) or contact us on [Discord](https://discord.gg/S3MVaC9) in the `#plugins` channel.

# Supported devices
Artemis can support any device supported by the Chroma SDK but in order to identify which device is which, we need a `PID` which is an ID unique to Razer products.

| Device                                       | Type     | Has layout |
|----------------------------------------------|----------|------------|
| Razer BlackWidow Ultimate 2012               | Keyboard | No         |
| Razer BlackWidow Classic (Alternate)         | Keyboard | No         |
| Razer Anansi                                 | Keyboard | No         |
| Razer BlackWidow Ultimate 2013               | Keyboard | No         |
| Razer BlackWidow Stealth                     | Keyboard | No         |
| Razer DeathStalker Expert                    | Keyboard | No         |
| Razer BlackWidow Chroma                      | Keyboard | No         |
| Razer DeathStalker Chroma                    | Keyboard | No         |
| Razer Blade Stealth                          | Keyboard | No         |
| Razer BlackWidow Tournament Edition Chroma   | Keyboard | No         |
| Razer Blade QHD                              | Keyboard | No         |
| Razer Blade Pro (Late 2016)                  | Keyboard | No         |
| Razer BlackWidow Chroma (Overwatch)          | Keyboard | No         |
| Razer BlackWidow Ultimate 2016               | Keyboard | No         |
| Razer BlackWidow X Chroma                    | Keyboard | No         |
| Razer BlackWidow X Ultimate                  | Keyboard | No         |
| Razer BlackWidow X Tournament Edition Chroma | Keyboard | No         |
| Razer Ornata Chroma                          | Keyboard | No         |
| Razer Ornata                                 | Keyboard | No         |
| Razer Blade Stealth (Late 2016)              | Keyboard | No         |
| Razer BlackWidow Chroma V2                   | Keyboard | No         |
| Razer Blade (Late 2016)                      | Keyboard | No         |
| Razer Blade Pro (2017)                       | Keyboard | No         |
| Razer Huntsman Elite                         | Keyboard | No         |
| Razer Huntsman                               | Keyboard | No         |
| Razer BlackWidow Elite                       | Keyboard | No         |
| Razer Cynosa Chroma                          | Keyboard | No         |
| Razer Blade Stealth (Mid 2017)               | Keyboard | No         |
| Razer Blade Pro FullHD (2017)                | Keyboard | No         |
| Razer Blade Stealth (Late 2017)              | Keyboard | No         |
| Razer Blade 15 (2018)                        | Keyboard | No         |
| Razer Blade Pro 17 (2019)                    | Keyboard | No         |
| Razer BlackWidow Lite (2018)                 | Keyboard | No         |
| Razer BlackWidow Essential                   | Keyboard | No         |
| Razer Blade Stealth (2019)                   | Keyboard | No         |
| Razer Blade 15 (2019) Advanced               | Keyboard | No         |
| Razer Blade 15 (2018) Base Model             | Keyboard | No         |
| Razer Cynosa Lite                            | Keyboard | No         |
| Razer Blade 15 (2018) Mercury                | Keyboard | No         |
| Razer BlackWidow (2019)                      | Keyboard | No         |
| Razer Huntsman Tournament Edition            | Keyboard | No         |
| Razer Blade 15 (Mid 2019) Mercury            | Keyboard | No         |
| Razer Blade 15 (Mid 2019) Base               | Keyboard | No         |
| Razer Blade Stealth (Late 2019)              | Keyboard | No         |
| Razer Blade Pro (Late 2019)                  | Keyboard | No         |
| Razer Blade 15 Studio Edition (2019)         | Keyboard | No         |
| Razer Blade Stealth (Early 2020)             | Keyboard | No         |
| Razer Blade 15 Advanced (2020)               | Keyboard | No         |
| Razer Blade 15 (Early 2020) Base             | Keyboard | No         |
| Razer Blade Stealth (Late 2020)              | Keyboard | No         |
| Razer Ornata Chroma V2                       | Keyboard | No         |
| Razer Cynosa V2                              | Keyboard | No         |
| Razer Orochi 2011                            | Mouse    | No         |
| Razer DeathAdder 3.5G                        | Mouse    | No         |
| Razer Abyssus 1800                           | Mouse    | No         |
| Razer Mamba 2012 (Wired)                     | Mouse    | No         |
| Razer Mamba 2012 (Wireless)                  | Mouse    | No         |
| Razer Naga 2012                              | Mouse    | No         |
| Razer Imperator 2012                         | Mouse    | No         |
| Razer Ouroboros 2012                         | Mouse    | No         |
| Razer Taipan                                 | Mouse    | No         |
| Razer Naga Hex (Red)                         | Mouse    | No         |
| Razer DeathAdder 2013                        | Mouse    | No         |
| Razer DeathAdder 1800                        | Mouse    | No         |
| Razer Orochi 2013                            | Mouse    | No         |
| Razer Naga 2014                              | Mouse    | No         |
| Razer Naga Hex                               | Mouse    | No         |
| Razer Abyssus 2014                           | Mouse    | No         |
| Razer DeathAdder Chroma                      | Mouse    | No         |
| Razer Mamba (Wired)                          | Mouse    | No         |
| Razer Mamba (Wireless)                       | Mouse    | No         |
| Razer Mamba Tournament Edition               | Mouse    | No         |
| Razer Orochi (Wired)                         | Mouse    | No         |
| Razer Diamondback Chroma                     | Mouse    | No         |
| Razer DeathAdder 2000                        | Mouse    | No         |
| Razer Naga Hex V2                            | Mouse    | No         |
| Razer Naga Chroma                            | Mouse    | No         |
| Razer DeathAdder 3500                        | Mouse    | No         |
| Razer Lancehead (Wired)                      | Mouse    | No         |
| Razer Lancehead (Wireless)                   | Mouse    | No         |
| Razer Abyssus V2                             | Mouse    | No         |
| Razer DeathAdder Elite                       | Mouse    | No         |
| Razer Abyssus 2000                           | Mouse    | No         |
| Razer Lancehead Tournament Edition           | Mouse    | No         |
| Razer Atheris (Receiver)                     | Mouse    | No         |
| Razer Basilisk                               | Mouse    | No         |
| Razer Naga Trinity                           | Mouse    | No         |
| Razer Abyssus Elite (D.Va Edition)           | Mouse    | No         |
| Razer Abyssus Essential                      | Mouse    | No         |
| Razer Mamba Elite (Wired)                    | Mouse    | No         |
| Razer DeathAdder Essential                   | Mouse    | No         |
| Razer Lancehead Wireless (Receiver)          | Mouse    | No         |
| Razer Lancehead Wireless (Wired)             | Mouse    | No         |
| Razer DeathAdder Essential (White Edition)   | Mouse    | No         |
| Razer Mamba Wireless (Receiver)              | Mouse    | No         |
| Razer Mamba Wireless (Wired)                 | Mouse    | No         |
| Razer Viper                                  | Mouse    | No         |
| Razer Viper Ultimate (Wired)                 | Mouse    | No         |
| Razer Viper Ultimate (Wireless)              | Mouse    | No         |
| Razer DeathAdder V2 Pro (Wired)              | Mouse    | No         |
| Razer DeathAdder V2 Pro (Wireless)           | Mouse    | No         |
| Razer Basilisk X HyperSpeed                  | Mouse    | No         |
| Razer DeathAdder V2                          | Mouse    | No         |
| Razer Viper Mini                             | Mouse    | No         |
| Razer DeathAdder V2 Mini                     | Mouse    | No         |
| Razer Naga Left-Handed Edition               | Mouse    | No         |
| Razer Firefly Hyperflux                      | Mousepad | No         |
| Razer Firefly                                | Mousepad | No         |
| Razer Goliathus                              | Mousepad | No         |
| Razer Goliathus Extended                     | Mousepad | No         |
| Razer Firefly v2                             | Mousepad | No         |
| Razer Kraken 7.1                             | Headset  | No         |
| Razer Kraken 7.1 Chroma                      | Headset  | No         |
| Razer Kraken 7.1                             | Headset  | No         |
| Razer Kraken 7.1 V2                          | Headset  | No         |
| Razer Kraken Ultimate                        | Headset  | No         |
| Razer Kraken Kitty Edition                   | Headset  | No         |
| Razer Nostromo                               | Keypad   | No         |
| Razer Orbweaver                              | Keypad   | No         |
| Razer Tartarus                               | Keypad   | No         |
| Razer Orbweaver Chroma                       | Keypad   | No         |
| Razer Tartarus Chroma                        | Keypad   | No         |
| Razer Tartarus V2                            | Keypad   | No         |
| Razer Tartarus Pro                           | Keypad   | No         |