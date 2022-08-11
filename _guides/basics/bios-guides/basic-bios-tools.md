---
layout: wiki
title: Basic Bios Tools
description: "Basic bios tools to backup / dump/ restore your bios incase of a bios failure"
parent: Bios Guides
grand-parent: Basics
contributors:
discord: pppig233666#9264
---

# Basic Bios Tools

Bios tools enable you to do basic ``backup / dump/ restore`` if you DON'T want to lose any board info in case a BIOS update / mod / whatever failed and you have flashed an empty BIOS then you need your board info back.

## How to use

- Extract it somewhere
- The do the following:
1. To dump your current BIOS, go to Scripts and run _dump_BIOS.Ink
2. To backup all your Lenovo Variables, go to Scripts and run ``_backup.cmd`` as admin. A log file will be opened in notepad to monitor progress
- Your info should be backed up and stored in **bios_backup / LVAR_backup** folder
- Save them in the cloud just in case you need it someday 
- **(optional)** If step ``2`` has been done and you lost your board info due to whatever reason, go to ``Scripts`` and run ``_restore.cmd`` as admin and a log file will be open in notepad to tell the progress
- Download the bios tools from [here](https://laptopwiki.eu/wp-content/uploads/2021/11/BIOS_tools.7z){:target="_blank"}

{: .Tip}
Always check the files you download
