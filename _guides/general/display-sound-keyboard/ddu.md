---
layout: wiki
title: Display Driver Uninstall
description: "Uninstall the Display Driver due to bugs or power limited issues with the GPU"
parent: Performance, Thermal and Fan Management
grand_parent: General
contributors:
discord: ['GhostFella#4719, ⫶ ℜ𝔲𝔦𝔫 ♡#9472']
---

# Uninstall video driver on Laptop (DDU) and Install new video driver

{: .tip}
Make sure Hybrid Mode is enabled to avoid any issues that might appear.

## Procedure

1. Download DDU [Display Driver Uninstaller](https://www.wagnardsoft.com/){:target="_blank"}
2. Download latest Nvidia or AMD Driver of your choice (you can download an older version as well for Nvidia if it is known to performs better than newer ones since that's the case nowadays) or Check Discord Server for most stable Driver

    [Nvidia Driver Download](https://www.nvidia.com/Download/Find.aspx?lang=en-us){:target="_blank"}
    [AMD Driver Download](https://www.amd.com/en/support){:target="_blank"}
3. Extract DDU on your desktop or a familar place in your Computer
4. Place the display driver(s) either in same folder with DDU or together on your desktop
5. Disable your internet connection, both Wi-Fi and Ethernet (Can type "Network Connections" in your search bar and right click on any that appear and set them to "Disable" until you're done)
6. Hold the **SHIFT** key and select Restart to restart your laptop in safe mode
7. You will select from the upcoming screen the following
```
Troubleshoot - > Advanced options - > Startup Settings - > click on Restart
```
8. Select the option Number **4**  called  **Enable Safe Mode** by pressing "4" on your keyboard
9. Open DDU, close the options window. On the right side on  ``---Select device type---``  select **GPU** and below it choose whichever one you are trying to uninstall **(AMD or Nvidia)**
10. On the left side  choose "Clean and restart"
11. After the restart, install the recommended AMD/Nvidia driver
12. Reboot and enable your internet connection (see step 5)
    -  Do not forget to turn your Hybrid Mode OFF after you are done with everything (in case you were playing/using the laptop with it off already.)

## Video Tutorial

Follow this general video tutorial on how to perform DDU and rid your system of buggy drivers

<iframe width="400" height="225" src="https://www.youtube.com/embed/bP-2B14Nckw" title="How to do a Clean Graphics Card Driver Installation - DDU Tutorial - GPU Driver Uninstall" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>