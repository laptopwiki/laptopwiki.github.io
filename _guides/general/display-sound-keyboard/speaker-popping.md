---
layout: wiki
title: Speaker Popping
description: "Speaker popping after audio stops playing"
parent: Display, Sound and Keyboard
grand_parent: General
image: https://media.discordapp.net/attachments/852210156875153408/955908527724068894/unknown.png
contributors:
discord: ['amq#1035']
---

# How to get rid of the popping sound in speaker after an audio stops playing

- Open ``Regedit``
- search for ``ConservationIdleTime``
- Replace values of ``ConservationIdleTime``, ``IdlePowerState``, ``PerformanceIdleTime`` with ``01 00 00 00 4``. repeat this for all, **use F3 to find next** If regedit complains that value cannot be changed, just continue to next