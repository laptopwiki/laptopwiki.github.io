---
layout: wiki
title: BIOS Recovery
description: "Recovering bricked BIOS in Legions using a SPI"
parent: Bios
grand_parent: Legion
contributors: ['labodj'] 
---

# Recovering bricked BIOS in Legions using a SPI

## My Legion Laptop BIOS is screwed up and I don't have a BIOS backup, how can I try to restore it?

A 3.3V SPI programmer like the CH341A is needed and also knowledge about it is required. This [video](https://www.youtube.com/watch?v=4qX2zihB6UE){:target="_blank"} should help to understand how the programmer works, if you still can't figure out how SPI works, then this guide isn't for you.

### Step 0: Prepare your tools

Prepare your SPI, SPI software, install HxD and 7-Zip.

### Step 1: Backup

The very first thing to do is to have a backup of your BIOS, there are 2 paths here:

- You already have a backup at least of BIOS region (usually 16MB), go to step 2, and skip step 3.
- You don't have a backup, continue here...

If you don't have a backup (very bad thing!) you should make one now, it's not mandatory but it's required if you want to restore your serials/OS keys afterwards.

Obviously if your laptop is bricked to make a new backup you'll need to perform a SPI DUMP from the IC containing BIOS region (usually 16MB), dump it and ***verify the dump against IC content*** with the software you're using (NeoProgrammer 2.2.0.8 was used during my testing).

### Step 2: Clean vendor BIOS file

You can build a config-less, serial-less BIOS using the one provided by Lenovo following these steps

- Download the BIOS from Lenovo site
- Start the downloaded ``.exe`` and select to extract it in a convenient folder (eg: desktop/bios/)
- Open the folder, you will find an .exe file (eg: BiosName.exe)
- Extract it with 7-zip using task menu function ``right click on the file -> 7-Zip -> Extract in "BiosName"`` don't mind for errors, they are normal.
- Open the new folder just created, there is a **BIOS.fd** file, that is the BIOS file we want to trim to 16 MB, it's larger due to the fact it contains firmwares for other ICs and programming instructions.
- Start HxD and open BIOS.fd file
- ``Ctrl+E, start: 97D050 | length: 1000000 | Hex, OK``
- ``Ctrl+C, Ctrl+N, Ctrl+V, Enter, Ctrl+S``
- Save this file in the convenient folder with a proper name, eg ``lenovo_clean.bin``

This will be the new 16MB BIOS region image, you can now flash this file using a programmer to the BIOS IC, you will lose any config/serial/OS key, but at least it should boot, if you have a BIOS backup and you want recover your serials/OS keys please proceed to step 3.

### Step 3 (optional): Inject your serials

Your 16MB backup file: ``backup.bin``

- Open HxD
- Open ``lenovo_clean.bin`` in HxD
- Open ``backup.bin`` in HxD
- Select ``backup.bin`` tab if not already selected
- ``CTRL+E, Start: D0000 | Length: C6000 | Hex, OK``
- ``CTRL+C``
- Select ``lenovo_clean.bin`` tab
- ``CTRL+E, Start: D0000 | Length: C6000 | Hex, OK``
- ``CTRL+V``
- File, Save As, ``lenovo_clean_mySerials.bin``

This will be the new 16MB BIOS region image, without config but with your serials/OS keys.

### Step 4: Flash

You can now flash the new 16MB BIOS image to rhe 16MB BIOS IC using SPI, verify the flash with the software you're using to do the flash procedure and try to boot.
