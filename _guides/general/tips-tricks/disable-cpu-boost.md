---
layout: wiki
title: Disable CPU Boost
description: "Disabling CPU Boost to achieve better temperatures"
parent: Performance, Thermal and Fan Management
grand_parent: General
contributors:
discord: ['amq#1035']
---

# Disable CPU Boost

In the previous guide, disabling boosting was suggested via adjusting the max state to 99%. The flaw with this method is capping the CPU at only 1.7GHz (AMD 5000H series)[^1]. To maintain stock 2.9/3.0GHz clock with boosting disabled, use this method below instead of 99% max power state.

## Setup

- Using Registry Editor, go to ``HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Contro l\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\be337238-0d82-4146-a960-4f3749d470c7`` and select ``Attributes``. Modify the value of “Attributes” from **1** to **2**. Data should read “0x00000002 (2)”. This will uncover a hidden power option.

- Navigate to 
```
Edit Power Plan --> Edit Plan settings for your current plan --> Change advanced Power Settings --> Processor Power Management
```
and a new tab under these options called the **Processor Performance Boost Mode** will appear. Set it to ``Disable`` and click ``Apply``. Also, make sure your max processor state is at 100%. The CPU will now run on the stock base frequency.

{: highlight}
For a general idea about the performance compared to 99% max state, average FPS went up to about 5-15 with the temperatures still maxing out at the same 75 degree Celsius! The FPS loss from 99% disabled has been recovered while maintaining the benefit! Tiering your games at 1.7GHz, 3.0GHz, and full boosting will allow greater flexibility for performance and temperatures.

# Disable CPU Boost (Simpler Method)

-  Run cmd as administrator

```
powercfg -attributes sub_processor perfboostmode -attrib_hide 
```

- To undo this Operation

```
powercfg -attributes sub_processor perfboostmode +attrib_hide
```

## Configure in Power Plan

```
Control Panel / Power Options / Change Plan Settings / Change advanced power settings / Processor power management / Processor performance boost mode
```

- While Disabled (Default: Aggressive), your thermals will improve drastically with minimal (CPU intensive games) or zero performance lost. If you don't want to completely disable it use Efficient Aggressive, as Efficient Aggresive uses 3ghz by default and will boost only in programs that require higher CPU clocks.


# References

## Footnotes

[^1] [Asus ROG G15(2020) Reddit Discussion by user deenokun](https://www.reddit.com/r/ZephyrusG14/comments/g7kd5b/comment/fq9d6sn/?utm_source=share&amp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Butm_medium=ios_app&amp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Bamp%3Butm_name=iossmf){:target="_blank"}