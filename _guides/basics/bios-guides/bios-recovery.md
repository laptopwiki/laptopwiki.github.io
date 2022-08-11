---
layout: wiki
title: Bios Recovery
description: "Recovering OS keys/serial from old Bios with a programmer"
parent: Bios Guides
grand-parent: Basics
contributors:
discord: LABØ!#5022
---

# Recovering OS keys/serial numbers from old BIOS

## My Legion Laptop BIOS is screwed up and I don't have a BIOS backup, how can I try to restore it?

Basically a 3.3V SPI programmer like the CH341A is needed and also knowledge about it is required. This [video](https://www.youtube.com/watch?v=4qX2zihB6UE){:target="_blank"} should help to understand how the programmer works, if you still cant figure out how this programmer works, then this guide isn't for you. 

## Steps to flash the bios

You can build a config-less, serial-less BIOS using the one provided by Lenovo following these steps

- First of all, it's better to dump the current non-working BIOS using the SPI programmer. **DUMP IT** and **VERIFY** the dump with the software you're using (NeoProgrammer 2.2.0.8 was used in my testing). You can recover your own serials/os keys from the broken BIOS, there will be another guide for that, but you need to have a good dump for that.
- Install HxD, 7-Zip
- Download the BIOS from Lenovo site
- Start the downloaded ``.exe`` and select to extract it in a convenient folder (eg: desktop/bios/)
- Open the folder, you will find an .exe file (eg: BiosName.exe)
- Extract it with 7-zip using task menu function ``right click on the file -> 7-Zip -> Extract in "BiosName"`` don't mind for errors, they are normal.
- Open the new folder just created, there is a **BIOS.fd** file, that is the BIOS file we want to trim to 16 MB, it's larger due to the fact it contains firmwares for other ICs and programming instructions.
- Start HxD and open BIOS.fd file
- ``Ctrl+E, start: 97D050 | length: 1000000 | Hex``
- ``Ctrl+C, Ctrl+N, Ctrl+V, Enter, Ctrl+S``
- Save this file in the convenient folder with a proper name, eg ``lenovo_clean.bin``
- You can now flash this file using a programmer to the BIOS IC, you will lose any config/serial/os key, but at least it should boot.
