---
layout: wiki
title: Slow Wifi after SLeep
description: "WIfi becomes slow when woken up from sleep"
parent: Tips and Tricks
grand_parent: General
contributors:
discord: ['mind12#3390']
---

# Slow Wifi after Sleep

Do you experience locked and slow wifi speed after resuming from sleep, **around 25-35Mb/sec** with Intel AX cards? The problem is the following however none of the settings helped me to resolve it. I'm on the latest Intel AX210 driver. Refer this [link](https://www.reddit.com/r/Surface/comments/dp96pb/psa_workaround_for_slow_wifi_after_waking_from/) for ppl with similar issues.

## Workaround

The only workaround that worked is creating a PowerShell script that is triggered by the sleep power event and disconnects then connects to my SSID. Even resetting the WIFI adapter had not helped. If anyone has the same issue feel free to create a scheduled task and run the PowerShell script with the following commands.

```
# Create scheduled task trigger: On event Log: System - Power-Troubleshooter - Event ID 1
# Wait 5 sec so the card reconnects after sleep.
start-sleep 5
$ConnectedWifi = netsh wlan show interfaces | Select-String '\sSSID'
$ConnectedWifi_Name = ($ConnectedWifi[0] -replace "SSID                   : ","").Trim()
netsh wlan disconnect
netsh wlan connect name=$ConnectedWifi_Name`

```

## Scheduled Task action

```
Start a program
Program/script: powershell
Add arguments: -windowstyle hidden -File "Your_ps_file_location"

```
