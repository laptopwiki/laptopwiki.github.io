---
layout: wiki
title: Opening / Changing Advanced Power Options
description: "Opening / Changing Advanced Power Options using .bat files"
parent: Tips and Tricks
grand_parent: General
contributors:  
discord: ['ecto UK/ES#2667']
---

# Opening / Changing Advanced Power Options using .BAT files

{. :highlight}
This could be useful if you want to quickly change settings in your power plan based on what your laptop is doing.

## Shortcut to open advanced settings

Create a new text document and copy/paste the line from below Then save it

```
AdvPowerSettings.batcontrol.exe powercfg.cpl,,3
```

## How to change settings

Create a new text document and copy/paste one of the lines from below and Save it as

<Current Scheme> Boost Disabled
-------------------------------

```
powercfg.exe /SETACVALUEINDEX SCHEME_CURRENT 54533251-82be-4824-96c1-47b60b740d00 be337238-0d82-4146-a960-4f3749d470c7 000
powercfg.exe -S SCHEME_CURRENT
```

<Current Scheme> Efficient Aggressive
-------------------------------------

```
powercfg.exe /SETACVALUEINDEX SCHEME_CURRENT 54533251-82be-4824-96c1-47b60b740d00 be337238-0d82-4146-a960-4f3749d470c7 004
powercfg.exe -S SCHEME_CURRENT
```

## Boost Mode Index Numbers

The last 3 digits of the above commands can be changed to the following for the various boost modes

```
Possible Setting Index: 000 - Disabled
Possible Setting Index: 001 - Enabled
Possible Setting Index: 002 – Aggressive
Possible Setting Index: 003 - Efficient Enabled
Possible Setting Index: 004 - Efficient Aggressive
Possible Setting Index: 005 - Aggressive At Guaranteed
Possible Setting Index: 006 - Efficient Aggressive At Guaranteed
```

## Other things that are possible

- Change which power mode you’re in (Silent, Balanced, High Performance)
- Change any settings within these power plans
- Change other settings such as sleep/wake timers 

![Examples shown above](https://cdn.discordapp.com/attachments/840314972918644767/857226400054378526/unknown.png)

"file needs to be added here, guide not complete"