---
layout: wiki
title: Add 60Hz Refresh Rate
description: "Adds 60Hz to monitors/laptops with no 60Hz refresh rate"
parent: Getting Started
grand-parent: Basics
contributors: ['ammarasyad'] 
---

# How to add 60Hz refresh rate to my laptop?
This guide works for any laptop/monitor. Tested on Legion 5 15IMH05H. You can also add unusual refresh rates (69Hz) and resolutions (1920x800), but do it at your own risk. For the purpose of this guide, we will not touch resolution.

## Download
Download CRU from this link: [cru-1.5.1.zip](https://www.monitortests.com/download/cru/cru-1.5.1.zip)


Extract the zip file somewhere, and then open the extracted folder and open `CRU.exe`.

## Adding the new refresh rate
In **Detailed Resolutions** there should only be one resolution defined, which is your resolution and its refresh rate.

![image](https://user-images.githubusercontent.com/20443208/169091697-c57fa661-0f53-4061-a602-9485b9cda66f.png)

Click on the resolution, then click **Edit...**

Your values might be different from this picture. **Do not touch the values here other than refresh rate unless you know what you're doing.**

![image](https://user-images.githubusercontent.com/20443208/169092230-960b307b-585e-4c84-a7f1-0010a938f514.png)


Click **Copy**, then close the dialog.

Afterwards, you're back on CRU's main screen. Click **Add...**, then click on **Paste**.

Edit the **Refresh Rate** to anything you want, but for the purpose of this guide, change it to 60.

![image](https://user-images.githubusercontent.com/20443208/169092332-c132a7b7-51d9-42d5-bdf0-428c9259cf17.png)

Click OK. Make sure the resolution and the refresh rate is as desired.

It will show up like this.

![image](https://user-images.githubusercontent.com/20443208/169094250-6d4e7752-7778-42eb-a48d-d9a4ef9abb7b.png)


## Applying changes

Close CRU, then open `restart64.exe`.

Your screen will refresh. If after 10 seconds your screen does not come back, press F8 to restore everything back to its defaults.

You're done. You can change your refresh rate in Windows `Settings -> System -> Display -> Advanced display -> Choose a refresh rate`.

If, for whatever reason, your new refresh rate/resolution is not displayed, click on `Display adapter properties for Display -> List all modes`. 60Hz will be displayed alongside your resolutions.
