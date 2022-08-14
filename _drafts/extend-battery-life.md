---
layout: wiki
title: Extend Battery Life
description: "Achieve best Battery Life using community made Powerplan"
parent: Tips and Tricks
grand_parent: General
contributors: ['kirakenchin', 'undervolt'] 
discord: ['Kuri#9378', 'NU7SU#3194']
---

# Extend battery life using community made power plan

This is a guide intended to boost your machines battery life (especially for brand new laptops)

## Steps

- **Hybrid Mode**
Make sure your Hybrid mode is enabled (Vantage/Legion Toolkit), in case you have a laptop equipped with advanced optimus (AO), use hwinfo and determine if the dedicated GPU is using power as there’s a known bug with AO not fully “killing” the DGPU after going back into Optimus mode. To “kill” the DGPU use this guide [Turn off Nvidia GPU in hybrid mode](https://laptopwiki.eu/index.php/guides-and-tutorials/performance-thermal-and-fans-management/how-to-turn-off-the-nvidia-dgpu-in-hybrid-mode/)

- **Battery calibration**
I you have a newly bought laptop or a laptop that has been plugged in for a long time, then Calibrate the battery by discharging to 15-20% then charging back to 100%, repeat this process until you get the normal discharge rate of 11-15w, usually takes 2-3 times for battery discharge to get that low.

- **Refresh Rate**
Use [Refresh Rate and Power Profile Auto-Switch V2](https://laptopwiki.eu/index.php/guides-and-tutorials/tips-tricks/auto-refresh-rate-power-plan-switcher/) to switch to 60Hz automatically when the device is unplugged

- **Powerplans**

  - Use Kira’s Quiet Mode V1 [⬇️](https://drive.google.com/file/d/1iAFuKj1Fcic0W3sN4Kk_akZFN3ADmuZF/view?usp=sharing) (AMD)

  - Use Kira Quiet Mode v2 [⬇️](https://drive.google.com/file/d/13F0SpoUK3vFm1WmQuqAhAXbyaqSuoFP5/view?usp=sharing) (AMD)

  - Use Undervolt's Battery saver plan [⬇️](https://drive.google.com/file/d/192udkM0IJCpmuIx2B_rx78UcXlLHeBuW/view?usp=sharing)(Intel)

## Importing Powerplan

- Open an [elevated command prompt](https://winaero.com/blog/how-to-open-elevated-command-prompt-in-windows-10/)

- Type the following command to list all the available power plans:

``powercfg.exe /L``

- Now all the power plans installed in the laptop will be displayed along with their GUID, currently equipped power plan will be denoted by an asterisk (*)
Execute the following command: 

``powercfg import "%YourUserProfile%\Location of the powerplan downloaded right now\PowerPlan.pow" GUID`` 

(DONT COPY PASTE THIS COMMAND, ADD YOUR VALUES)

- Use ``Powercfg.exe /l`` to get the GUID for each powerplan

- Replace the GUID portion with the actual GUID value along with the location of the power plan file with its extension (*.pow)
[Example: powercfg.exe import “C:\Users\kira\Downloads\KiraQuietModeV2.pow” ddf002d4-7cae-4a92-a312-7eb843f2abe9]

- To confirm the power plan installation, navigate to ``windows search -> edit power plan -> Powerplan Name -> Enable``
