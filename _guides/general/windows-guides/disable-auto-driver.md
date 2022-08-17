---
layout: wiki
title: Disable Automatic Driver Updates
description: "A simple but effective way to disable windows 11 Automatic Windows Driver Updates"
parent: Windows Guides
grand parent: General
contributors: ['kirakenchin']
discord: ['⫶ ℜ𝔲𝔦𝔫 ♡#9472']
---

# DISABLE AUTOMATIC DRIVER UPDATES

>Short method to disable Windows Driver updates from being pushed through your automatic windows updates (thus preventing your nvidia or amd driver from being **automatically** installed without your approval and messing your current driver)

- Type in the search box **gpedit.msc**
- Go to **Computer Configuration** –> **Administrative Templates** –> **Windows Components** –> **Windows Update** –> **Manage updates offered from Windows Update** –> select and double click **Do not include drivers with Windows Updates** –> set it to **Enabled**

{: .highlight}
If you manually click on ``Check for Updates`` Inside your Windows Update, these Updates will still be offered. If you do want to avoid these driver updates (mainly nvidia or amd for some), you have to download and use ``WuShowHide`` by opening it and select ``Hide Update`` and let it scan and show you which updates it can hide. You select them from there. Do watch this [video](https://youtu.be/dJrGeBeruxM){:target="_blank"} if you do not have any idea on how wushowhide works

{: .warning}
**Gpedit.msc** is only available on the Pro version of Windows, not Home. It is possible to make it appear on home with a specific [tweak](https://www.itechtics.com/enable-gpedit-windows-10-home/){:target="_blank"}

>Wushowhide can not only be used for NVIDIA and AMD display drivers, but also for other drivers offered by Lenovo such as caps lock OSD, monitor drivers, bios updates etc as well as windows updates too

General updates that should usually be avoided at all costs from your Windows Updates list and not done for your laptop’s safety:** Nvidia Display Driver** & **BIOS update**

{: .warning}
Bios update should only be done when there is a need for a fix that was caused by previous updates or there is an incremental feature update that will improve the experience of your laptop
