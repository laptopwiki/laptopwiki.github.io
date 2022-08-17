---
layout: wiki
title: Windows Power profiles with Quiet CPU boosting
description: "Power Profiles designed to keep CPU boost on but reduce overall noise levels"
parent: Performance and Thermal Management
grand_parent: General
contributors: [''] 
discord: ['amq#1035']
---

# Windows Power Profile - Poor Man's Edition

The main idea behind this Guide is to keep the CPU boost enabled in games while the CPU draws lower power than necessary, leading to lower noise levels. 

# Profile Settings

## Quiet

```
min cpu: 81%
boost: aggressive
amd power slider: better performance
```
### End Result

```
single core: 4.3-4.4 GHz @ 21W
all cores short: 3.0 GHz @ 40W
all cores sustained: 2.5 GHz @ 25W
in fortnite ultra: 4.0 GHz @ 25W
```

## Balanced

```
min cpu: 81%
boost: aggressive
amd power slider: better battery
```
### End Result

```
single core: 4.3-4.4 GHz @ 22W
all cores short: 3.6 GHz @ 58W
all cores sustained: 3.4 GHz @ 48W
in fortnite ultra: 4.0 GHz @ 27W
```

## Performance

```
min cpu: 100%
boost: aggressive
amd power slider: battery saver
```
### End Result

```
single core: 4.3-4.4 GHz @ 22W
all cores short: 3.8 GHz @ 70W
all cores sustained: 3.8 GHz @ 70W
in fortnite ultra: 4.1 GHz @ 30W
```
