---
layout: wiki
title: Turn off dedicated graphics card
description: "Switch off the Nvidia GPU after an external Monitor is disoconnected"
parent: Performance, Thermal and Fan Management
grand_parent: General
contributors:
discord: ['LABØ!#5022']
---

# Turn off dedicated Graphics card

This Guide provides insight on manually switching off the dedicated graphics card of a laptop, once an external Monitor is disconnected.

## Problem

Nvidia GPU would'nt get switched off completely when in hybrid mode, hence the battery life of the laptop decreases immensely, leading to mediocre battery life in a laptop.

In Detail, The problem can be described as the external Display outputs of a gaming laptop (HDMI / USB-C) are directly connected to the discrete GPU. Any time an external monitor is used, the discrete GPU is the default Grpahics card that handles the external display. Any app (or system background processes/daemons) that is launched after the external monitor is connected uses the dedicated graphics card as default. If the system is started with an external monitor attached, even more processes/apps/services/daemons use the discrete GPU. When we disconnect the external monitor, we expect that apps using the discrete GPU will be transferred to the power saving Internal Graphics card. For example, in the case of Nvidia, We can check if any remaining app is running in the Nvidia GPU using the Nvdia GPU activity monitor activated through the Nvidia Control Panel in the system tray. If any app is still running, we can kill it, closing it or using the task manager. Now the Nvidia GPU activity monitor is gray, no app is running, it should be fine, but it’s not. Using HWinfo64, we can clearly see that the dGPU is active in idle state, consuming 10/12 W to do nothing. It’s not HWinfo64 that is waking up the Nvidia dGPU, HWInfo64 wakes it up only when started in sensor mode only. This leads to an usually unsolvable and strange behaviour.

## Solution

There is a tool called [nvidia-smi](https://developer.nvidia.com/nvidia-system-management-interface){:target="_blank"}, which can be launched using a terminal. Using nvidia-smi one can check if there is any other process running on the Nvidia GPU. 

In fact, there are some processes that are not listed in the Nvidia GPU activity monitor. If these processes shown in the Nvidia-SMI are killed, the Nvidia GPU will then turn off. This problem was initially found in this [forum post](https://forum-en.msi.com/index.php?threads/issue-with-nvidia-optimus-on-msi-gs65.317379/post-1949576){:target="_blank"}. The Author of the post is talking about the very same problem encountered by most owners of laptops with a discrete GPU nowdays. In this post, the Author shared a PowerShell script that can be run to restart any process running on the Nvidia GPU. 

## Tool

The tool can be found [here](https://github.com/eduojeda/nvidia-optimus-kill){:target="_blank"}. This tool was tested by fellow members of the server and it was found to be working as expected. In order to run it, a PowerShell terminal needs to be open and the following command pasted.

## Command

```
Set-ExecutionPolicy RemoteSigned
```

In the future, the bat file **Nvidia-kill.bat** or **Nvidia Kill Link** could be run as a quicker access.

## Pictures

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2021/11/smi-before-300x188.png)
*SMI Before*

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2021/11/smi-after-300x188.png)
*SMI after*
