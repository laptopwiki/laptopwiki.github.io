---
layout: wiki
title: Optimus, Mux & Advanced Optimus
description: "Highlighting information about optimus, mux and advanced optimus and differences between them"
parent: Useful Information
grand_parent: General
image: https://media.discordapp.net/attachments/852210156875153408/955908527724068894/unknown.png
contributors: ['M164'] 
---

# Optimus, MUX switch and Advanced optimus

## Optimus

Most laptops with come with optimus by default. It's the simplest, but the most ineffective solution when it comes to gaming. With regular optimus, the display output is routed through the iGPU, which takes a small performance hit. Usually in the range of 10-15%. On top of it, since the iGPU is always on, a part of the RAM will stay reserved for the iGPU and off limits for other use. Might not be such an issue for devices with 32GB RAM, but can become an issue on 16GB devices and will be utterly crippling on those with just 8GB, which is already not enough for gaming. 

However, for example on Lenovo Legion laptops, all external ports, such as HDMI and USB-C, are connected to the dGPU. Because of this, even if you have hybrid mode enabled, you are bypassing the iGPU and take no performance hit on the external screen.

## Mux Switch

MUX switch allows switching off the iGPU, but you need to restart the device. When the iGPU is off, the display output won't be routed through the iGPU, so there will be no performance hit, and no RAM will be reserved for the iGPU.

## Advanced Optimus

Advanced optimus allows to bypass the iGPU, without having to have it disabled with a MUX switch, so no restart needed. The choice between iGPU and dGPU can be made while the laptop is running, and there will be no performance hit. In theory, the best solution, as it allows both the best battery life, as well as best gaming performance, at the click of a single button. In practice, the solution tends to be a bit buggy, which is why many users still prefer the solution with MUX switch, even though it requires a restart to switch between "best battery life" and "best gaming performance" options. 