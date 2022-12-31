---
layout: wiki
title: AMD Display Driver Install
description: "Guide to install the latest AMD GPU driver"
parent: Display, Sound and Keyboard
grand_parent: General
image: https://media.discordapp.net/attachments/852210156875153408/955908527724068894/unknown.png
contributors: ['kirakenchin'] 
discord: ['Atvaark#0664']
---

# Installing AMD latest driver

This Guide should help you to install stable AMD display drivers and remove buggy display drivers that have been plaguing your Laptop 

{: .tip}
This fix has been tested on Windows 11 and hence i cannot guarantee it works on Windows 10 too.  But i don’t see the reason why it wont. Still, Windows 10 Users try it at your own risk

## Simple Fix

1. Download latest driver from [AMD](https://www.amd.com/en/support){:target="_blank"}

{: .center}
![Selecting your Hardware](https://laptopwiki.eu/wp-content/uploads/2022/03/Screenshot-2022-03-28-193158.png)
*Selecting your Hardware*

2. Before installing the driver, make sure to enable factory reset

{: .center}
![Enable Factory Reset option](https://laptopwiki.eu/wp-content/uploads/2022/03/image-2.png)
*Enable Factory Reset option*

3. Restart PC to hybrid mode and AMD installer will install the downloaded AMD driver. Restart PC again.

4. Check for Updates inwindows update, once old AMD driver installs again, go to 

   ```
   Device Manager --> Display Adapters --> AMD display adapter --> Properties --> Driver Tab --> Roll back Driver
   ```

5. Now the driver would get rolled back to the previous manually installed driver from AMD Website

## Detailed Fix

1. Download latest driver from [AMD](https://www.amd.com/en/support){:target="_blank"} or **22.5.1/22.7.1** as those are optimised drivers that were tested by community members

{: .center}
![Selecting your Hardware](https://laptopwiki.eu/wp-content/uploads/2022/03/Screenshot-2022-03-28-193158.png)
*Selecting your Hardware*

2. Download [**Wushowhide**](https://download.microsoft.com/download/f/2/2/f22d5fdb-59cd-4275-8c95-1be17bf70b21/wushowhide.diagcab){:target="_blank"}

3. DDU current AMD driver using this [Guide](https://laptopwiki.eu/index.php/guides-and-tutorials/performance-thermal-and-fans-management/ddu-install-guide/){:target="_blank"}

4. Restart PC and then don't connect to the internet. After restarting to hybrid mode, the only display adapter should be **Microsoft Basic Display Adapter**.

5. Once that has been confirmed, install the **latest AMD driver** or **22.5.1/22.7.1** that was previously downloaded.

6. Once it has been installed, restart pc and boot to hybrid mode again, run the WUshowhide program and search for **AMD driver deployed from Microsoft**, disable that update and then u will never get this issue ever again.

7. Open Radeon software and check the version.

Now, you have successfully avoided the nightmare. You can update to latest AMD driver from now on, without any issues. Happy latest driver always from AMD site!

## Windows 10 – Driver fails to install, causes Black screen/ Flickering

In such an event
- Boot to safe mode, DDU the latest driver and restart pc with internet enabled.
- Go to windows update and search for updates. It will auto install AMD driver.

If you ever want to install latest driver, then you need to be in Windows 11
