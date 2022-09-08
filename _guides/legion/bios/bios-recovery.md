---
layout: wiki
title: BIOS Recovery
description: "Recovering bricked BIOS in Legions using a SPI"
parent: Bios
grand_parent: Legion
contributors: ['labodj'] 
---

# Recovering bricked BIOS in Legions using a SPI

## Disclaimer

This guide has been written after many tests on a Legion 7 16ITHg6, using a CH341A as SPI and NeoProgrammer 2.2.0.8 as SPI Software, if you have a different laptop/software/SPI keep in mind that you'll need to adapt the following information.

## My Legion Laptop BIOS is screwed up and I don't have a BIOS backup, how can I try to restore it?

A 3.3V SPI programmer like the CH341A is needed and also knowledge about it is required.

This video should help you to understand how this kind of programmers work, if you still can't figure out how SPI works, then unfortunately this guide isn't for you.

<iframe width="892" height="502" src="https://www.youtube.com/embed/4qX2zihB6UE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Tools needed

- SPI & SPI software (NeoProgrammer 2.2.0.8 was used during my testing)
- [HxD](https://mh-nexus.de/en/hxd/){:target="_blank"}
- [7-Zip](https://www.7-zip.org/){:target="_blank"}
- [Innoextract](https://github.com/dscharrer/innoextract){:target="_blank"}
- BIOS software tools like FPTW64.exe

### Know your BIOS

Your BIOS is usually a 24MB image written on one or more IC, in my case 2 ICs:

- IC1 - 8MB: BIOS descriptor, Intel ME Region...
- IC2 - 16MB: BIOS region

We are interested on the 16MB BIOS region.

### Step 1: Backup your BIOS

The very first thing to do is to have a backup of your BIOS.

There are 2 kind of backups:

- Full dump: the largest you can do, in my case 24MB (8MB + 16MB)
- BIOS region dump: in my case 16MB

There are 2 paths here:

***You already have a backup***

- It's a full dump: you need to trim BIOS region with HxD.
- It's a BIOS region dump: you're good to go.

If your backup is known to be a "working" one you can flash it, go to step 4.

***You don't have a backup***

You should make one now, it's not mandatory but it's required if you want to restore your serials/OS keys afterwards.

- Your laptop can boot: you're able to perform a software dump, for Intel platform I suggest FPTW64, you can use it the following way:
  - ``FPTW64.exe -d BACKUP_FULLDUMP.bin`` for the full dump.
  - ``FPTW64.exe -d BACKUP_BIOSREG.bin -bios`` for the BIOS region dump.

- Your laptop is bricked: to make a new backup you'll need to perform a SPI DUMP from the IC containing BIOS region (usually 16MB one), dump it and ***verify the dump against IC content*** with SPI software.

### Step 2: Clean vendor BIOS file

You can build a config-less, serial-less BIOS using the one provided by your vendor, start by downloading the BIOS update from vendor website, the downloaded .exe file can be "protected" or not, the goal here is to extract something like ``BIOSVERSION.exe`` from the vendor installer.

***"unprotected" setups***:

- Start the downloaded installer ``.exe`` and select to extract it in a convenient folder (eg: desktop/bios/).
- Open the folder, you will find requested ``BIOSVERSION.exe`` file.

***"protected" setups***:

- Drag installer ``.exe`` file over ``innoextract.exe``, it will create a folder with requested ``BIOSVERSION.exe`` file.

***

Now that you have ``BIOSVERSION.exe`` file you can proceed to extract ``BIOS.fd`` file from it:

- Extract it with 7-zip using task menu function ``right click on the file -> 7-Zip -> Extract in "BiosName"`` don't mind for errors, they are normal.
- Open the new folder just created, there is a **BIOS.fd** file, that is the BIOS file we want to trim to 16 MB, it's even larger than 24MB due to the fact it contains programming instructions.
- Start HxD and open BIOS.fd file
- ``Ctrl+E, start: 97D050 | length: 1000000 | Hex, OK``
- ``Ctrl+C, Ctrl+N, Ctrl+V, Enter, Ctrl+S``
- Save this file in the convenient folder with a proper name, eg ``bios_clean.bin``

This will be the new 16MB BIOS region image, you can now flash this file using a programmer to the BIOS IC, you will lose any config/serial/OS key, but at least it should boot, if you have a BIOS backup and you want recover your serials/OS keys please proceed to step 3.

### Step 3 (optional): Inject your serials

Your 16MB backup file: ``BACKUP_BIOSREG.bin``

- Open HxD
- Open ``bios_clean.bin`` in HxD
- Open ``BACKUP_BIOSREG.bin`` in HxD
- Select ``BACKUP_BIOSREG.bin`` tab if not already selected
- ``CTRL+E, Start: D0000 | Length: 4230 | Hex, OK``
- ``CTRL+C``
- Select ``bios_clean.bin`` tab
- ``CTRL+E, Start: D0000 | Length: 4230 | Hex, OK``
- ``CTRL+V``
- File, Save As, ``bios_clean_mySerials.bin``

This will be the new 16MB BIOS region image, without config but with your serials/OS keys.

### Step 4: Flash

You can now flash the new 16MB BIOS image to rhe 16MB BIOS IC using SPI, verify the flash with SPI software and try to boot.
