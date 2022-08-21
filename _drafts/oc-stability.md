---
layout: wiki
title: Overclocking and Stability testing
description: "Overclocking the GPU to achieve better performance than stock"
parent: Performance, Thermal and Fan Management
grand_parent: General
contributors:
discord: ['tidles#19239']
---

# GPU Overclock Guide

This Guide was made for maximising Overclock Potential on 30 series GPUs based on personal experiences.
 
## Setup

The main aimn for this guide is to find the maximum frequency for every voltage which is in the range of being hit on maxium loads. The most easiest way to test for stability was by using 3DMark´s Stress test, FireStrike and TimeSpy (2 displays are needed – One Display with stresstest open and the other one with [MSI Afterburner](https://www.guru3d.com/files-details/msi-afterburner-beta-download.html){:target="_blank"} and [HWinfo](https://www.hwinfo.com/download/) open){:target="_blank"}.

## Alt-tabbing

3DMark benches do stop when you alt tab out. Other games, benches or alike will go down with fps and load when being in background, Hence avoid alt tabbing during benchmarks.

### Consequences of ALT Tabbing

Consequent Alt TAB will make the GPU switch over to a higher frequency when being on load after a short time. So with non constant load and consistent Alt TAB might need to wait this out every time depending on how fast you are.

### How does this exactly behave?

You have applied a certain curve. After some time on load (sometimes seconds, sometimes close to one minute) this whole curve will be shifted up by 30Mhz. This means when you are testing clocks on load and type the exact same clocks later in the curve when being in idle the load, clocks will be 30Mhz higher leading to instabilities.

### Frequency Clocks

The frequenzy steps are a bit annoying too. It´s mostly 7, Sometimes 8 in few others. The load curve shift is mostly 30. Sometimes 29. Because of this you have to find out the exact clocks you are using in the curve later on. If you type another number it is gonna be changed to a number available from the steps. This might lead to instabilities too if not taken care of. You can read out these numbers easily thru OSD activated thru MSI Afterburner. Look this [video](https://www.youtube.com/watch?v=1pHuv8Ndc2Y){:target="_blank"} if you are not aware on how to activate OSD. Just write them all down so you know each step you went across.

## Actual testing

- Open MSI Afterburner.
- **Shift click** the whole curve as far you can downwards with beeing able to still see the first dot in the line.
- Click the first frequency dot on **0,700mV** and pull it up to **1400MHz**. This should be stable to start with and make the curve flat at 1400 MHz over the whole graph. Thus the GPU will be picking only the first voltage from where the frequency isn’t climbing anymore.
- Apply.
- Open Stress test (Explained previously)
- Let it run until curve shifts 30 MHz up, Should stay at 1430 MHz now.
- Now increase the Curve by **7 MHz**. Wait one or two cycles of the test. Increase by 7 MHz again.
- Repeat until you get **crashes/artifacts**. Artifacts can be identified by **"green squares"**, **"yellow arcs"**, **"white circles"** and so on.
- Due to artifacts, go 7 MHz back. Wait 3-5 cycles for crashes/artifacts (If you get a driver crash: try to click in the now black stress test windows FAST and click „ESC“. This should close the stress test after a maximum of 1 minute and you can restart it thru 3DMark and keep on tweaking. If you cannot get 3DMark to react you have to force close every component or fit thru the task manager and open again.
- The GPU using small steps makes it very pleasant to tweak (at least for me) because the number of full driver crashes were at around 4 or 5 in a 3 hour session. Artifacts just need fast clock adjustment and you can keep it running.
- Now when you didn’t find artifacts or crashes after 3-5 cycles write down the achieved clock with the used voltage. I would recommend going at least 3 steps (21 MHz) below the short-term stability you just tested in your final curve to have a pretty stable Overclock.

{: .highlight}
Follow the above mentioned steps until you reach around **0,850mV**. Because at this voltage you will start to get tdp throttling in certain loads. Further stability testing is really time consuming and should be happening over time when gaming. Because you will hit tdp throttling very often at above 0,85V the voltage will fluctuate by a lot.

Most modern games will make very good use of 0,85V maxing out closely around it and you will already have close to max performance

Some example values to help

{: .center}
![image](https://media.discordapp.net/attachments/884779035991875615/884785769460416542/unknown.png?)

# Voltage-Frequency Curves

## 3060 Laptop

- Follow the guide above to fine tune the 3060, since it was made by user with a 3060 Legion 5 pro

{: .center}
![image](https://cdn.discordapp.com/attachments/832668125098803261/1009573060623470692/unknown.png)
*3060 Undervolt Curve*

## 3070 / 3070ti Laptop

- Open MSI afterburner settings turn on everything in the ``General`` and ``Compatibility`` sections
- set core clock to lowest and apply (around 100 - 150 is recommended)
- press ``ctrl + F`` to open voltage-Frequency table
- drag the point at 750mV to 1600MHz and apply (gpu clock will settle at 1590 or 1605)
- the table should now be a sharp increase with a plateau starting at 750mV onwards

### Alternate Simple Overclock

- Apply target clock at a singular voltage and be done with it. not much perf difference if you pick the correct voltage point
e.g. 800mV: 1710MHz
- The voltage can be 750mV or 800mV or 850mV or 900mV. Anything above these values wont provide more performance
- Memory clock can be left at +300 due to not much performance increase at higher clocks

{: .center}
![image](https://cdn.discordapp.com/attachments/713356473123602484/1009798514789843034/unknown.png)
*3070/ti Undervolt Curve*

## 3080 / 3080ti Laptop

- Open MSI Afterburner
- Start with +140 on core clock and +500 on memory clock
- Then press ``ctrl + F`` to open the voltage-Frequency table and follow the following points
    -  At 0.781 and above set points to 145 
    - At 0.806 and above set points to 150
    - At 0.825 and above set point to 155
    - At 0.831 and 0.837 set points to 160
- The cut-off should be at 0.837v

### Alternate Simple Overclock

- Apply target clock at a singular voltage and be done with it. Not much perf difference if you pick the correct voltage point
e.g. 837mV: 1780MHz
- The voltage can be 831mv or 837mv or 850mv or 900mv or 950mv. Anything above these values won't provide more performance
- Memory clock can be left at +500 due to not much performance increase at higher clocks

{: .center}
![image](https://cdn.discordapp.com/attachments/713356473123602484/1009800464449151006/unknown.png)
*3080/ti Undervolt Curve*

