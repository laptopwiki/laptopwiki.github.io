---
layout: wiki
title: Quickly draining Battery in Hybrid mode
description: "Battery draining quickly in hybrid mode due to dgpu being active"
parent: Tips and Tricks
grand_parent: General
contributors: ['martin4x4'] 
discord:
---

# Problem: dGPU is always active when in Hybrid mode, and battery drains too fast

## Solution

- Click on ``Start > Control Panel > Nvidia Control Panel``.
- Click on the ``Desktop menu > Display GPU Activity Icon`` in Notification Area.
- On the taskbar, in the right corner, there will be a new icon. Point your mouse over it and find out which application is using the dGPU
- Open Nvidia Control Panel
- Go to 3D settings -> Manage 3D settings
- Set the guilty app to use iGPU instead

![image](https://media.discordapp.net/attachments/859207621408063498/877790609115590696/unknown.png?width=380&height=300)

![image](https://images-ext-1.discordapp.net/external/0MxXyAqtnyGELdeUmu3B2DCH7QBFKoTiS6G1QXxZDKI/%3Fpid%3DImgDet%26rs%3D1/https/th.bing.com/th/id/OIP.2qdn2mE14sgwJbwc37OxXQAAAA)