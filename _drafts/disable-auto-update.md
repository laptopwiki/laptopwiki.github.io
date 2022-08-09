---
layout: wiki
title: Disable Automatic Windows Update
description: "A simple and effective way to disable automatic windows update"
parent: Windows Guides
grand parent: Basics
contributors: ['kirakenchin']
discord: ⫶ ['ℜ𝔲𝔦𝔫 ♡#9472']
---

# Disable Automatic Windows Updates

>Disclaimer: Welcome to Manual Windows Updates. From now on, windows wont sneaky update your laptop without your permission. Since this is manual update, the End-User needs to check for updates manually everytime.
>_A well rewarded hassle in the end_

## Windows 11 Pro

### Creating the registry to enable Manual Updates


- Open Windows Search and type in ``regedit`` or ``registry editor``, right click on it and open it as administrator
- Navigate towards
```
HKEY_LOCAL_MACHINE –> SOFTWARE –> Policies –> Microsoft –> Windows –> WindowsUpdate –> AU
```
If you do not have the **AU folder**, you will have to create it: Right click on the ``Windows Update folder –> select “New” –> Key``. Rename the newly created folder to **“AU”**
- After clicking on the AU Folder, on the right side there will be a tab with Name, Type & Data. Right click inside it and hit ``New –> DWORD (32-bit) Value``. Rename the created Registry to **AUOptions** , double click on it and set its value data as **2** and Base as Hexadecimal. (Value as 2 = to notify before downloading an update)
- Repeat previous step and create another **DWORD (32-bit) Value**, renaming it to ``AutoInstallMinorUpdates``. This time setting its Value data to **0**. (0 = to treat minor updates like the other updates (_by default windows is silently installing these minor updates_))
- Create another DWORD (32-bit) Value called ``NoAutoRebootWithLoggedOnUsers`` and set it’s Value data to **1** (1 = The user decides whether to restart or not to restart his/her computer (_by default windows would choose to restart in the next 5 minutes_))
- Create final DWORD (32-bit) Value called ``NoAutoUpdate`` and set it’s value data to **1** (1 = Disabling Automatic Updates (_this is by default enabled_))


![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-2.png)

### Group Policy Editor


Close Registry Editor and head towards the search box once again and type ``gpedit.msc`` (this will only work for Windows 11 Pro users, for Home version see below)
Head towards 
```
Computer Configuration –> Administrative Templates –> Windows Components –> Windows Update –> Manage updates offered from Windows Update
```
- Double click on **Select when Preview Builds and Feature Updates are received** set it to **Enabled** and in the box below, where it asks **How many days you would like to postpone an update before your device receives it” type 3**. This will make sure that you will always receive stable updates and not their unstable new version that might contain issues/bugs and so on.

![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-7.png)

- Again in Group Policy Editor, head over to 
```
Computer Configuration –> Administrative Templates –> Windows Components –> Windows Update –> Manage End-User Experience
```
look for the **Configure Automatic Updates** double click on it and set it to ``Disabled``. This will prevent Windows from downloading updates automatically for you.

![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-10.png)

- For Windows 11 HOME users, following this [guide](https://www.youtube.com/watch?v=7wkgwEhtqdI){:target="_blank"} will help you add the Group Policy Editor to your windows and you will be able to do the above guide just like the Pro users.


### Windows 10 Pro


- Type in the windows search box **gpedit.msc** (Group Policy Editor), open it as administrator by right clicking on it and proceed the following route
```
Computer Configuration –> Administrative Templates –> Windows Components –> Windows Update
```
Look inside for an option called **Select when Preview Builds and Feature Updates are received** double click on it and set it to ``Enabled`` and in the box below where it says ``Preview Build – Fast`` set it to **Semi-Annual Channel**.
- Again in Group Policy Editor, head over to 
```
Computer Configuration –> Administrative Templates –> Windows Components –> Windows Update
```
look for the **Configure Automatic Updates** double click on it and set it to ``Disabled``. This will prevent Windows from downloading updates automatically for you.

![image](https://laptopwiki.eu/wp-content/uploads/2022/08/image-8.png)

For Windows 10 HOME users, following this [guide](https://www.youtube.com/watch?v=7wkgwEhtqdI) will help you add the Group Policy Editor to your windows and you will be able to do the above guide just like the Pro users.

{: .warning}
DO NOT FORGET TO REGULARLY (once a month – recommended) TO HIT THE **CHECK FOR UPDATES** BUTTON! – We are not responsible for your problems if you do not bother updating for a year and then you get a ton of updates waiting when you press check. 

>This method is for preventing Microsoft from pushing you broken updates for your Windows 10/11, **BIOS Updates** and **GPU Driver** updates automatically causing new issues everyday. Before every time you decide to hit ``Check for Updates” it is recommended to run [WUShowHide](https://www.majorgeeks.com/files/details/wushowhide.html) by clicking “Hide Updates” and if it scans and finds anything called **Firmware/BIOS** or **Display Driver** (AMD or NVIDIA) it is recommended to check the box for them and hide them to prevent any further conflicts that might appear. Windows installing them will only bring issues or overwrite your current drivers. Check this video for help with Wushowhide.

_Bid farewell to borken updates_
