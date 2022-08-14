---
layout: wiki
title: Enable Hidden CPU Boost Mode
description: "How to enable hidden CPU Boost Mode"
parent: Tips and Tricks
grand_parent: General
contributors: [''] 
discord: ['mind12#3390'] 
---

# Enable Hidden CPU boost mode

## Show hidden CPU Boost Mode without the Regedit trick

- Run Command Prompt / Windows Terminal as administrator:

``powercfg -attributes sub_processor perfboostmode -attrib_hide``

In order to Undo this action

``powercfg -attributes sub_processor perfboostmode +attrib_hide``

-  Configure it in your preferred power plan

```
Control Panel --> Power Options --> Change Plan Settings --> Change advanced power settings --> Processor power management --> Processor performance boost mode
```

    - While Disabled (Default: Aggressive) your thermals will improve drastically whith minimal (CPU intensive games) or zero performance lost. If you don't want to completely disable it use Efficient Aggressive.


## Show System cooling policy in the power plan settings

By default the option should be visible, but sometimes due to upgrading windows, the option might get hidden

```
powercfg -attributes sub_processor syscoolpol -attrib_hide
```

In order to Undo this action

```
powercfg -attributes sub_processor syscoolpol +attrib_hide
```