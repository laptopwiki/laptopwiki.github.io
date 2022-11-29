---
layout: wiki
title: Vbios Flashing Guide
description: "Detailed Guide on Flashing VBIOS for your Laptop - fixing your GPU issues or increasing Performance"
parent: Performance, Thermal and Fan Management
grand_parent: General
contributors: ['Kirakenchin']
discord: ['Coleh#4297'] , ['aaalbert#1784'] 
---

# Necessity of Flashing a VBIOS

Most of the time, if you want additional power gain that leads to performance gain or if you have issues with current stock / custom flashed VBIOS

# How to properly flash a VBIOS

- Prepare a bootable memory stick with a fat32 format (NTFS disk won't work properly and will lead to boot error issues).
- Flashing VBIOS is recommended to be done in DOS to avoid any complications.
- In case of laptop VBIOS flashing with a different oem VBIOS, then make sure to use the **NVFlash ID Mismatch Modified version** that allows you to flash regardless of the board. (adds a layer of risk, where the flash must be done in windows. Additionally, the program would not stop or warn when a bad flash is done)

## Process Pre-requisites

- NVflash
- NVflash Mismatch ID disabled version
- USB stock with Fat32 format
- GPU rom file (can be found in our archives)

As a first, format the USB stick to FAT32 format and then copy the contents of the folder nvflash.zip (https://www.techpowerup.com/download/nvidia-nvflash/) or nvflash mismatch ID disabled version (https://www.techpowerup.com/download/nvidia-nvflash-with-board-id-mismatch-disabled/) and the desired VBIOS in the form of the ROM file into the disk.

## Method

- Paste the contents of **NVflash** (normal or mismatch disabled) in drive C:/ of your laptop. Name the folder in any preference you would like. Use Normal edition if you want to flash lenovo bios, use mismatch ID disabled edition for flashing VBIOS from another OEM such as MSI

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-12.png)
*Location of NVflash*

- You may want to disable the GPU device because it can crash when you flash the card and forcing the computer to restart. To disable the device go to

`Windows Device Manager --> Display Adapters. Then Right Click --> Disable Device`

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-13.png)
*Disable GPU*

- open Windows Command Prompt as Administrator by typing "CMD" in the search bar. Alternatively, Windows 11 users can also use Windows Terminal
{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-14.png)
*Command Prompt*

- After opening you want to find that folder at the Root of **C:/** and launch the program. You can follow the commands and adjust the naming accordingly

```
cd/```
Hit Enter
```
dir```
Hit Enter
```
cd/nvflash64```
Hit Enter (Inside folder)
```
nvflash64```
Hit enter((this will run the program called nvflash64.exe in that folder. If you have the program named differently, you will need to type that name instead)

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-15.png)
*NVflash*

Now that it is shown, how the program runs, you can quit it by pressing **Q**. Next, we follow the following steps to make sure the device doesn't get bricked in the process.

- **Back up the current BIOS before doing anything else**
⋅⋅⋅1. Type **nvflash64 -b backup.rom** and hit Enter
Nvflash64 is the program, -b is the command to back up, and backup.rom is the name given to the backup BIOS. The backup.rom name can be changed to anything else, according to user preference, but its better to keep it simple to be able to find the rom file later. Once backed up, make sure to check the folder to make sure it saved and make a copy on a flash drive in case you need to re-flash the card with a different computer. If you are doing this in DOS then you already have it on the flash drive.

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-19.png)
*Backing up ROM*

- **Flashing the GPU**
⋅⋅⋅2. Now the BIOS is backed up, it is time to flash the card. If you are using the modified mismatch ID disabled version type `"nvflash64 --protectoff"` to disable the lockout (two dashes --). Otherwise, skip this step.


{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-20.png)
*Disable Protection while using modified version*

## Actual flashing part
- Type `nvflash64 -6 (ROM NAME).rom` and hit Enter. 
It will ask you a few times if you really want to do this. Follow the prompts and wait for it to finish flashin

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-21.png)
*Flashing in progress*

## Video Tutorial
> If any doubt about flashing the GPU or still not sure about flashing, check the video below.

<a href="http://www.youtube.com/watch?feature=player_embedded&v=ihTNBLoprDQ
" target="_blank"><img src="http://img.youtube.com/vi/ihTNBLoprDQ/0.jpg" 
alt="VBIOS Flash Guide" width="240" height="180" border="10" /></a>

## In case of a Brick 
Follow this guide if you end up bricking the card in this process
https://laptopwiki.eu/index.php/docs/re-flashing-soft-bricked-30-series-gpu/