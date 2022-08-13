---
layout: wiki
title: First Time Checklist
description: "A checklist to help you with your brand new laptop"
description: "Detailed new laptop checklist"
parent: Getting Started
grand_parent: General
contributors: ['averyspeedybird', 'kirakenchin'] 
---

# First Time Checklist

## The ultimate first time checklist guide to help you getting started with your new laptop!
- [ ] Check box for obvious shipping damage
- [ ] Check laptop for dents and scratches
- [ ] Check packaging (confirm new model)
- [ ] Check power brick and cord damage
- [ ] Check for cracks, fractures or impact marks
- [ ] Open and close lid (check hinges) (when setting up windows, don’t connect to wifi, therefore you won’t have to deal with unnecessary microsoft services)
- [ ] Verify actual specs are what you bought (hwinfo and model number)
- [ ] Check all keyboard keys multiple hits (enter key)
- [ ] Check for [dead pixels](https://lcdtech.info/en/tests/dead.pixel.htm){:target="_blank"} (black and white screen tests), Perform [Monitor Tests](https://arnowelzel.de/en/tools/monitor-test){:target="_blank"} too
- [ ] Check all ports working (check snugness and fit)
- [ ] Check profiles and fan speeds (noise)
- [ ] Check RGB across diff profiles (dark room and well lit)
- [ ] Check for backlight bleed
- [ ] Check trackpad for motion and click feel
- [ ] Check different resolutions
- [ ] Take [system image](https://www.youtube.com/watch?v=x9BGn4MivJw){:target="_blank"} “out of the box”
- [ ] Remove bloatware (McAfee, etc.)
- [ ] Update laptop software (lenovo vantage/dragon center/armory crate, if available)
- [ ] Update bios (with laptop software, if available)
- [ ] Update GPU driver
- **About bios and GPU driver updates, make sure to check whether to update or not with other users first just in case something important's changed or if there are known issues with it**
- [ ] Connect to wifi and run Windows update
- [ ] Charge battery and confirm 100% as start point
- [ ] Review Discord/Reddit for any new issues experienced by new owners
- [ ] Install Benchmarking and Hardware info tools
- [ ] Download flight sim and games
- [ ] Confirm benchmarks measure up to other users of same model (Cinebench for CPU, aida64 + heaven for combined load stress test, 3Dmark timespy/firestrike for an overall benchmark, shadow of the tomb raider for a non-synthetic benchmark)

## Benchmarks you can run on your Laptop to verify and compare performances

- 3DMark TimeSpy (CPU, GPU and global performance scores)
- Cinebench R23 (multi-core and single-core CPU performance)
- CrystalDiskMark (config set to SSD) for SSD read/write performance
- Built-in benchmark of the game Shadow of the Tomb Radier (free demo) with settings set to HIGHEST, once at native resolution and once at 1080p
- No benchmark specific to RAM, as it is part of the global CPU performance

It is also very highly recommended to run a [combined load stress test](/guides/general/getting-started/stress-test/){:target="_blank"} to check your thermal performance out of the box.

## Conditions for Result Submissions [to our discord](https://discord.gg/CtDvEHecHn){:target="_blank"}  

|  Paramters | Values |
| :-------------: |:-------------:|
| Mux mode | dGPU (hybrid mode disabled) |
| OC | OFF |
| Power profile | performance | 
| Cooling | Back lifted | 
| Power supply | plugged-in |
| Temperature Limit | Gen 6 110c (AMD) 100c (Intel) : Gen 7 95C (AMD) 95C (INTEL) |

|  Sharing results | Posting format (e.g) |
| :-------------: |:-------------:|
| Device | Legion 5 pro |
| CPU | 5800H |
| GPU | RTX 3070|
| RAM | 32gb [stock] or [HyperX] |
| Mux mode | dGPU | OC OFF or ON + applied parameters |
| Power profile | performance Cooling | Back lifted |
| Nvidia Driver | 511.23 |

The above conditions are only for comparing your results to the other laptops on our discord server, feel free to run benchmarks with other parameters if you want to.

## Extra
Legion specific items: 

- You could use [Legion Toolkit](https://github.com/BartoszCichecki/LenovoLegionToolkit/releases/tag/2.3.1){:target="_blank"} instead of vantage if you would like lower resource consumption 
- It is generally not recommended to update the BIOS version with Legion laptops because lenovo has a habit of breaking things with each new bios release. **Always check with other users on the discord before considering updating the bios.**

Enjoy and have fun!

# References

[Source](https://rentry.org/laptopsetupguide){:target="_blank"}

<script type="text/javascript">
  $(document).ready(function(){
   $('.task-list-item-checkbox').prop("disabled", false); 
}); 
</script>
