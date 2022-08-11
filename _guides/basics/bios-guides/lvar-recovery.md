---
layout: wiki
title: LVAR Recovery
description: "Recover Model SKU after maintenance"
parent: Bios Guides
grand-parent: Basics
contributors: ['Dglt', 'undervolt']
---

# Recover Model SKU if lost after Laptop Maintenance

## Symptomps

Lenovo Vantage has the default interface rather than the gaming interface, and System Information is missing, e.g: Model Name: INVALID, Serial Number: INVALID plus some of the features in vantage which were previously there, missing.

## Tools

In order to recover the default values, we will use a command line based developer app called LVAR (Lenovo Variable Tool)

- First of all, download the linked [archive](https://laptopwiki.eu/wp-content/uploads/2021/11/LVAR.zip){:target="_blank"}, and then extract the folder inside it to ``C:/``. After that, open up an Admin Command prompt.
- Type ``cd C:/LVAR`` and hit ``enter``. You may want to run ``dir`` to double-check if you are in the right folder.

After checking it, now you can start running the commands. (For this, you need to know your default values) (RUN THEM ONE BY ONE!)

{: .Tip}In the following commands, make sure you have a 64-Bit OS. If you have a 32 Bit system, then use the 32 Bit version of the "Exe Commands", Example: **LvarWin32V229.exe /w /pjn /c "LNVNB161216"**

- ``LvarWin64V229.exe /w /pjn /c "LNVNB161216"``
- ``LvarWin64V229.exe /w /pn2 /c "LNVNB161216"`` (_For the motherboard model, it's same on all Legion's_)
- ``LvarWin64V229.exe /w /pn /c "Lenovo Legion 5 15IMH05H"`` (_Your full model name, change the "5 15IMH05H" to your model name, it's located on the sticker under the laptop or check Lenovo Vantage or Legion toolkit to check your model name and number_)
- ``LvarWin64V229.exe /w /fd /c "Legion 5 15IMH05H"`` (_Your model name once again, change the "5 15IMH05H" to your model name_)
- ``LvarWin64V229.exe /w /mt /c "8XXXXXXXX"`` (_Replace 8XXXXXXX with the MTM of your device, you can find it on the sticker under the laptop_)
- ``LvarWin64V229.exe /w /ln /c "PFXXXXXX"`` (_PFXXXXX is your serial number, it can be found either in Lenovo Vantage or Legion Toolkit_)
- After doing all that, restart, and you should have all of your info back, as well as the Vantage gaming features such as keyboard lighting.

{: .Tip}
Always check the files you have downloaded.
