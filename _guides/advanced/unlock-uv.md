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

Following the guide should unlock undervoling throught Throttlestop or XTU.

![image](https://user-images.githubusercontent.com/100846697/163895366-a685fac8-25c0-4c72-9821-9679a3e4d988.png)


## Supported List

This works on -
1. Legion 5i, 5i Pro and 7i
2. Acer Predator Laptops with H45 Intel Processors
3. Acer Nitro with H45 Intel Processors

This guide will be applicable for most InsydeH20 laptops. However you must check if your bit value is the same. 

## Preparation

Disable Secure Boot by going into BIOS > Boot > Secure Boot > Disabled. You can re enable secure boot once you unlock UV.

Note: You might have to set up an admin password to do this if the option is grayed out. (Use something easy to remember because you definitely don't want to forget that)

Download this tool and extract the contents inside the zip folder to ``C:\insyde-tool.``

After you do that, open ``cmd`` as administrator  then enter
```
cd C:\insyde-tool 
```
Ensure you are in the right folder by running the command ``dir``. It should output something like this.

![image](https://user-images.githubusercontent.com/100846697/163895181-7ae36a12-817d-45ba-9150-dcc36df9c877.png)


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

![image](https://user-images.githubusercontent.com/100846697/163895608-b18af097-0dde-4e5a-8375-8e80a0e44467.png)

{: .tip}
For 10th Gen - Row containing 000000D0. Column 6 when counting from the right.
For 11th Gen - Row containing 000000D0. Last Column.

After changing the bit value that's highlighted in the picture, save the file as vars-m.txt in the same directory.

## Flashing Vars
Go back to the same command prompt and run this last command
```
H2OUVE-W-CONSOLEx64.exe -sv vars-m.txt
```

To verify the modification is successful, check for the following entry based on the red underlined value taken earlier. Since mine is ``[05B]``, I should be looking for ``Variable Index[05b]: Set Successfully``
Ignore other lines.

![image](https://user-images.githubusercontent.com/100846697/163895647-a44ddac2-1acb-4465-b3af-f0275db13482.png)

Reboot and you should have undervolt working. Throttlestop shouldn't say locked anymore.

![image](https://user-images.githubusercontent.com/100846697/163896395-88295249-bc18-463e-bf2b-21a0ba68233b.png)


## Video Tutorial

The video was made for 10th gen. However most of the steps are same. For 11th gen be sure to change ``0xDF`` and not ``0xDA``. Read Editing Vars for more info.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lYSKzZRQcOA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# References

Original Guide Written by u/dglt1  
Edited for convenience.

[Notebook Review Archives](https://web.archive.org/web/20220125093526/http://forum.notebookreview.com/threads/lenovo-legion-5-and-7-2020.832593/page-27){:target="_blank")

[Legion Series DIscord](discord.gg/legionseries){:target="_blank"}

