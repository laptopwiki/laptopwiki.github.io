---
layout: post
title: HDMI 2.1 Fiasco
description: "Recent News clearing the doubts about HDMI 2.1 in Lenovo Legion Laptops"
tags: ['Legion','HDMI','HDMI 2.1','Standards']
image: https://cdn.discordapp.com/attachments/960201425063936033/960201584900452362/unknown.png
contributors: ['kirakenchin']
discord: ['Rowdyhorse4#0554']
---

# HDMI 2.1 Fiasco

## What is the issue with HDMI 2.1 in Lenovo Legion Laptops and why is it a big deal?

Lenovo Legion laptops do have HDMI 2.1 but due to the shared bandwidth between the internal display and video output, the external video output does not attribute complete HDMI 2.1 capability. Hence it is generally not possible to use 4k120 at its max possible output. This issue was escalated with Lenovo and following was the reply

An Official Answer:

{: .highlight}
_We’ve found the issue regarding the HDMI 2.1. It requires a minimum of 8 lanes to run at 4k at 120Hz but the configuration of the system’s bandwidth is divided into two. The other one is for the internal LCD uses and the other x4 lanes is for the HDMI 2.1 uses. If you can disable the internal display, its possible to increase the bandwidth. However, we cannot find this option in BIOS to disable it. As an alternative, you can use a USB-C to DisplayPort if your monitor has a DP 1.4a input. Additionally, the 10bit display is a color display of the monitor but in order to meet that, you need to have the right GPU and cable. The system design simply cannot output 10Bit display to an external monitor via HDMI 2.1 because its bandwidth is shared with internal monitor. You may try to open the file from this [link](https://lnv.gy/3yw0Omh) then look for page 83 or the block diagram. It will further explain how the system distributes the bandwidth_


Nevertheless, one of our knowledgeable owner (Rowdyhorse4#0554) has dived deep down in this fiasco in order to explain the actual issue with the HDMI port and clear this misconception of 4k120 being not at all a possibility.

![image](https://cdn.discordapp.com/attachments/960201425063936033/960201584900452362/unknown.png)

![image](https://cdn.discordapp.com/attachments/960201425063936033/960201605771313202/unknown.png)

## Terminology - Dithering

Dithering is when the computer artificially raises the bit depth to 10-bit via software techniques. The techniques used can be its own post so i'll leave it you to do self research but Physically the color output is still restricted to 8-bit. With good dithering however, the difference of 8-bit dithering and 10-bit can be almost inconceivable. RTINGS consider good 8-bit dithering as 10-bit in fact for their tests. (RTING mentions ["we consider 8-bit with dithering to be equivalent to 10-bit, as long as the 10-bit gradient looks smooth"](https://www.rtings.com/tv/tests/picture-quality/gradient){:target="_blank"}

## Preliminary Setup

Setting your Display via Windows Settings, your Windows settings will automatically allow 4k120hz when connected to a compatible HDMI 2.1 4K120hz tv. VRR/G-Sync will also be available in this mode. In order to allow this however with the Legion's HDMI limited bandwidth, 10-bit Color depth has to be sacrificed. To compensate, Windows/Nvidia will use Dithering to the signal to improve color accuracy. Using some RAW 4k DSLR images and Movies, I did a double blind test for Everyday Use with two people who are not knowledgeable about bit depth and they could not differentiate the color accuracy. However, this is using everyday software. Content creators using specialized software will still be able to tell the difference most likely.

{: .center}
![image](https://cdn.discordapp.com/attachments/960201425063936033/960202203354787861/unknown.png)
*4k120 @ 8Bit*

{: .center}
![image](https://cdn.discordapp.com/attachments/960201425063936033/960202252491063326/unknown.png)
*Gsync-Support*

Going down to 4K60Hz should allow windows automatically revert to 10-bit Color depth as this is just a question of bandwidth limitation. However there is a problem with this that will be discussed later on.

{: .center}
![image](https://cdn.discordapp.com/attachments/960201425063936033/960202566745079888/unknown.png)
*4k60 with 10bit support*

Likewise, going to any lower resolution in 120hz mode should also let windows automatically revert to 10-bit color depth.

{: .center}
![image](https://cdn.discordapp.com/attachments/960201425063936033/960202748442337370/unknown.png)
*QHD120@10Bit*

{: .center}
![image](https://cdn.discordapp.com/attachments/960201425063936033/960202788359524402/unknown.png)
*FHD120@10bit*

## The Caveat with 10Bit in lower Resolution

This is where the problem arises, although i haven't verified if this is limited to an LG TV issue or not. It's a software issue. Sometimes when you just plug in the TV or restart the laptop, The Signal is going to be locked to 8-bit Dithering mode despite being in lower than 4k Resolutions. When it is locked, the Signal output will be stuck in 4K120hz 8-bit despite having 2K selected as shown in the image.

{: .center}
![image](https://laptopwiki.eu/wp-content/uploads/2022/04/unknown-1-990x1024.png)
*QHD120 stuck in 8bit*

This can lead to worse resolution quality (Due to upscaling) and may also contribute to misconceptions about Lenovo's HDMI's abilities and disabilities. Checking via Nvidia Control Panel would leave bit depth option greyed out.

{: .center}
![image](https://cdn.discordapp.com/attachments/960201425063936033/960204084592406558/unknown.png)
*Greyed out bit depth in NVCP*

So far, the only solution I have found is to select a lower resolution in 60hz in the Nvidia Control panel, select use default Color settings at first. this would unlock the bit depth color mode.

![image](https://laptopwiki.eu/wp-content/uploads/2022/04/unknown-3.png)

select your desired resolution w/ 10bpc to maintain the signal output as you selected and result in Active output = Desktop mode.

![image](https://laptopwiki.eu/wp-content/uploads/2022/04/unknown-2-1024x958.png)

## 4k120 @ 10Bit a possibility?

There is no Method to force 4k120hz at 10-bit that I know of. This is the only Sacrifice that resulted from the bandwidth limitation that I'm aware off. Everything else should work. VRR, HDR, Dolby Vision, Dolby ATMOS (Audio), Dolby TrueHD (Audio), etc. whilst Lenovo's HDMI 2.1 is not Full-spec HDMI 2.1. It is still leagues more capable than HDMI 2.0. If you want to read more on why HDMI 2.1 has became such a mess, I suggest reading it [here](https://tftcentral.co.uk/articles/when-hdmi-2-1-isnt-hdmi-2-1){:target="_blank"}.

## Unverfied Information 1

I read/was informed at some point that the **HDMI bandwidth on Legion laptops is 32GBps instead of the full spec HDMI 2.1's 48GBps**. This would be more in-line with DisplayPort 1.4's standard which is also why Lenovo's HDMI 2.1 spec is suspiciously similar to DisplayPort 1.4 spec. I wouldn't be surprised if the HDMI 2.1 protocol is somehow tunnelled via DisplayPort (or uses DisplayPort spec) in the Laptop. The only thing that disproves this theory is the fact that half the needed PCIe lanes were sacrificed to support the internal display. Given that L5P uses PCIe v3, this however doesn't make sense as it would mean that the HDMI port shouldn't even support some HDMI 2.0 features, let alone HDMI 2.1. Hence i suspect that despite the sacrificed lanes, the HDMI bandwidth is still closer to 32GBps as the HDMI 2.1 port still allows most of HDMI 2.1's new feature at 4k120hz.

## Unverfied Information 2

I hear that using a lower Chroma Subsampling (YCbCR420) may unlock 4k120hz at 10-bit, I cannot test this as I have no monitors or TVs that would allow Nvidia control panel to use YCbCR420. the LG only accepts YCbCR444 at minimum and my FHD monitor only allows YCbCR422. If someone can verify this, it would be great.

{: .caution}
The obtained results are  a result of my own testing and knowledge/research of HDMI as a heavy audio visual enthusiast. If there are people who are experts in the field, feel free to correct me or discuss it with me if there are mistakes.
