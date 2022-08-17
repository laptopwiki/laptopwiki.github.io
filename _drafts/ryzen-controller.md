---
layout: wiki
title: Reduce CPU Temps - Ryzen Controller
description: "Reduce the CPU temps with the help of Ryzen Controller"
parent: Performance and Thermal Management
grand_parent: General
contributors: [''] 
discord: ['GhostFella#4719']
---

# Reduce CPU Temps - Ryzen Controller

This is a Guide to reduce the Temperature of AMD CPUs using Ryzen Controller (Ryzenadj). With the help of this software, various power management settings, such as limiting CPU power consumption can be adjusted. 

[Download](https://github.com/FlyGoat/RyzenAdj)

# Check Default Values - Ryzenadj.exe

- Download ryzenadj from above link
- Extract to C drive folder (eg. C:\ryzenadj-win64)
- Type ``cd`` to the folder where ryzenadj.exe is located (eg. cd C:\ryzenadj-win64)
- Type ``ryzenadj.exe –info``
- Your values will show up

# Automate Ryzenadj at Logon

- Download Ryzenadj and extract to a folder as mentioned above
- Open task scheduler
- Click on ``Create task``
- Give it a name
- Select ``Run`` with **Admin privileges**
- Select ``tab Triggers``, ``New``, ``at Log on`` or ``at Startup`` (your choice)
- Select ``tab Actions``, point to ryzenadj.exe (its in the folder), ``Argument -f 85`` (this is tctl-temp, 85 is the temperature, set it to any preferred value)
- Select ``tab Conditions``, uncheck ``Power (start on AC/stop)``
- Select ``tab Conditions``, uncheck ``Stop task``
- Click Ok 

For more information about how Ryzen Controller works, follow this [link](https://github.com/FlyGoat/RyzenAdj/wiki/Renoir-Tuning-Guide)