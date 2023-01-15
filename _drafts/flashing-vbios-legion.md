---
layout: wiki
title: Flashing VBIOS
description: "Flashing Legion VBIOS for higher TGP"
parent: Advanced
grand-parent: Legion
contributors: ['nonkerdoob'] 
discord: [nonkerdoob#0034] 
---

# Flash VBIOS for higher TGP in Legion Laptops

## Preparation

{: .warning}
Warning: This is an advanced guide and have potential risks that will damage your laptop and void warranty if done incorrectly. The guide is provided as is, and the user takes full responsibility if something happens to their device.

{: .warning}
If you ever get a Board ID mismatch, abort!

1. Switch to Hybrid Mode in Lenovo Vantage or Legion Toolkit
2. Backup Current VBIOS either with GPU-z or nvflash.
3. Just to be safe: Disconnect any peripherals connected to the dGPU (HDMI, USB-C)

## Backing Up the VBIOS

1. Download GPUZ - https://www.techpowerup.com/gpuz/
2. Open it and click on the Export Icon near BIOS version number. (Marked in the Screenshot below)

![image](https://user-images.githubusercontent.com/100846697/210909114-bc46060e-0264-4ea5-9fa9-f32b83673d80.png)

Alternatively you can use nvflash outlined in Method 2.

## Method 1: Lenovo Package

1. Download Lenovo package from Lenovo Website or the attachment below that is appropriate for your GPU.
2. Run it.
3. Reboot and you have higher TGP. Confirm by checking in Nvidia Control Panel > System Information.

If this method fails, try Method 2.

## Method 2: With Nvflash
1. Download Nvflash from - https://www.techpowerup.com/download/nvidia-nvflash/
2. Extract nvflash into ``C:\nvflash\``
  ![image](https://user-images.githubusercontent.com/100846697/210909374-0ce998a5-11cf-4503-84dc-98662aba2ecb.png)
3. Download VBIOS for your GPU from attachment below
4. Open CMD as admin, type in cd ``C:\nvflash\``. You can copy the path from address bar in File Explorer
5. Type dir to ensure you are in the right directory. You should see your ``VBIOS.ro``m and ``nvflashxx.exe`` files
6. Run these commands
**Backup**
    ```nvflash64.exe -b backup.rom```

**FLash**
    ```nvflash64.exe -f -6 <VBIOS file name>.rom```

{: .caution}
When flashing it might give you two warnings. Say yes to both.

![image](https://user-images.githubusercontent.com/100846697/210909387-e38b9d6b-b016-4a2b-9902-273b5f74ac7d.png)

7. Reboot
8. Confirm flash with Nvidia Control Panel > System Information

## Download Links

For Gen 6 users, you need custom mode to change cTGP and make use of VBIOS. It will have stock behavior in other modes. 

**3060**

Lenovo Package made for Legion 5i Gen 7. Can be installed in Gen 6.
Lenovo Link - https://download.lenovo.com/consumer/mobiles/legion5_15iah7h_rtx3060_140w-sign.zip
Mirror - https://cdn.discordapp.com/attachments/958324999532445716/1030666746224451614/legion5_15iah7h_rtx3060_140w-sign.zip

Lenovo Package made for Legion 5 Gen 7. Can be installed in Gen 6.
Lenovo Link - https://download.lenovo.com/consumer/mobiles/legion5_15arh7h_rtx3060_140w.zip
Mirror - https://cdn.discordapp.com/attachments/958324999532445716/1030667013259014204/legion5_15arh7h_rtx3060_140w.zip

ROM File - https://cdn.discordapp.com/attachments/958324999532445716/1021114009967140975/GA106.rom

**3070**

Lenovo Package made for Legion 5i Pro Gen 7. Can be installed on Gen 6.
Lenovo Link - https://download.lenovo.com/consumer/mobiles/legion5pro_16iah7h.exe
Mirror Link - https://cdn.discordapp.com/attachments/958324999532445716/1021110233709432922/legion5pro_16iah7h.exe

ROM FIle - https://cdn.discordapp.com/attachments/958324999532445716/1021111712545513472/249142.rom

**2060 Legion 5 85w to 115w**

Warning this VBIOS will not work on Y540 and Legion 7i 2020
ROM File and nvflash - https://cdn.discordapp.com/attachments/768238263525703702/819684558265516072/nvflash-legion5-100w-115w-new.zip



