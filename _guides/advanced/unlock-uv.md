---
layout: wiki
title: InsydeH20 Undervolt Unlock
parent: Advanced
contributors: ["dglt1","nonkerdoob"]
---

# Unlock Undervolting on InsydeH20 Bioses

{: .warning}
This is only meant for Intel laptops. AMD doesn't support undervolting on mobile CPUs yet.  
I am not responsible for any damage that might ensue from trying this yourself. 

## Supported List

This works on -
1. Legion 5i, 5i Pro and 7i
2. Acer Predator Laptops with H45 Intel Processors
3. Acer Nitro with H45 Intel Processors

## Preparation

Disable Secure Boot by going into BIOS > Boot > Secure Boot > Disabled. You can re enable secure boot once you unlock UV.

Note: You might have to set up an admin password to do this if the option is grayed out. (Use something easy to remember because you definitely don't want to forget that)

Download this tool and extract the contents inside the zip folder to ``C:\insyde-tool.``

After you do that, open ``cmd`` as administrator  then enter
```
cd C:\insyde-tool 
```
Ensure you are in the right folder by running the command ``dir``. It should output something like this.
[image]

{: .highlight}
If you only see a folder named "InsydeH2OUVE_x86_WINx64_200.00.01.00" or similar, bring the contents of that folder outside into "insyde-tool" or use the cd command to change the directory to that folder.

## Editing Vars

{: .warning}
Warning: always dump and edit fresh vars, using vars from a previous boot session may have a different order from the current boot and may cause problems. A bios update will lock the undervolt. This method might have to be redone to unlock it again. DO NOT USE VARS from an older bios or a previous session.

Once you are in the correct directory, run the following command to dump vars.
```
H2OUVE-W-CONSOLEx64.exe -gv vars.txt
```

The command should create a file named "vars.txt" in the folder where you extracted the tool to earlier.  Open with notepad to edit. CTRL+F and search for ``CpuSetup``. Find the value as shown in the screenshot. Additionally take note of the value underlined in red. (It varies on each vars extraction)
Change the value from ``01`` to ``00``.

After changing the value that's highlighted in the picture, save the file as vars-m.txt in the same directory.

## Flashing Vars
Go back to the same command prompt and run this last command
```
H2OUVE-W-CONSOLEx64.exe -sv vars-m.txt
```

and you're done, reboot and you should have undervolt working.

To verify the modification is successful, check for the following entry based on the red underlined value taken earlier. Since mine is ``[05B]``, I should be looking for ``Variable Index[05b]: Set Successfully``
Ignore other lines.


Original Guide Written by u/dglt1
Edited for convenience.

Video Tutorial - https://youtu.be/lYSKzZRQcOA (The value changed here is different. It has 0xDA while 11th gen Helios has 0xDF. Check highlighted image above.)
Basic Throttlestop and Undervolting Guide (After you unlock UV) - https://youtu.be/QCDIK-nnois
What did you just do?
Read here for an extensive guide.
It involves changing a bit that enables "Overclocking Lock" which prevents voltage and turbo ratio modifications through windows. The location of the bit for Helios 300 2021 (11th gen) bios is 0xDF. The guide may work for your non Helios laptop if it has insyde bios and you are able to correctly locate the bit required to edit.
Rather than relying on RUefi or other UFI shells to modify the vars, we used a method as shared by dglt here for the Legion 5.
Acer Gaming Discord Server - https://discord.gg/UF9eARcQQn
Legion Discord (Source of the guide) - https://discord.gg/legionseries
