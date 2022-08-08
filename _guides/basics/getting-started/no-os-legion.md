---
 layout: wiki
 title: Setup no OS legion
 description: "Setting up Legion laptops that come without an OS from factory"
 parent: getting-started
 grand-parent: basics
 contributors: 
 discord: ['ClemFab#0741', 'mind12#3390', 'nibi030#0077', 'Kazmir#7360', 'Kaobalt#0001'] 
 ---


# How to set up your no OS Legion

Basic Guide to setup Legion without an OS

- Go to BIOS and make sure Boot mode is set to UEFI
- Create a [bootable Windows USB media](https://www.youtube.com/watch?v=e4JMpOWPLKs){:target="_blank"} (ie. Rufus) and boot choosing the EFI drive on the boot menu pressing F12 (May need to disable SecureBoot in BIOS)
- Activate Windows
- Install Lenovo Vantage from the MS Store or [Legion Toolkit](https://github.com/BartoszCichecki/LenovoLegionToolkit/releases/latest){:target="_blank"} , switch to hybrid mode, restart, search for driver updates and install them. (Highly Recommend Legion Toolkit due to lower resource usage)
- Install Windows updates, If yoou choose the manual windows update mode, follow this [guide](https://laptopwiki.eu/index.php/docs/disable-automatic-updates-windows/){:target="_blank"}
- Install [Lenovo Hotkey](https://www.microsoft.com/en-us/p/lenovo-hotkeys/9pcmmnb260tx){:target="_blank"} from the MS Store
- Install Dolby Vision from the MS Store (if your screen supports it)
  - if the Dolby Vision still doesn’t start, then download the file “PQCONFIG.DV” and paste it in System32/spool/drivers/color
    “PQCONFIG.DV” file
    - [Legion 5 Pro 2021 (AMD)](https://drive.google.com/file/d/1IW_YgBNasq5NOHy2frQgBcmcMERsfdI5/view?usp=sharing){:target="_blank"}
    - [legion 5i Pro 2021 (Intel), Legion 7i 2021 (Intel)](https://laptopwiki.eu/wp-content/uploads/2022/02/PQCONFIG.zip){:target="_blank"}
    - [Legion 5 2021 (AMD)](https://drive.google.com/file/d/1A8iFxXSb2jBE88FB_c1XR1gAKOWjFGM7/view?usp=sharing){:target="_blank"}
    - [Legion 5i 2021 (Intel)](https://drive.google.com/file/d/18uoXAsuglse9EHDip2aM40IiplGv8gVs/view?usp=sharing){:target="_blank"}
- Install (rename the extension to .appx) the [HEVC Video Extensions](https://codecpack.co/download/hevc-video-extensions.html%20or%20open%20ms-windows-store://pdp/?ProductId=9n4wgh0z6vhq){:target="_blank"} for Dolby Vision
- Install the factory [Lenovo power profiles](https://laptopwiki.eu/wp-content/uploads/2021/11/LegionPowerPlan.zip){:target="_blank"}
- Install [Factory ICC profiles](https://newsupport.lenovo.com.cn/driveList.html?fromsource=driveList&selname=Lenovo%20Legion%20R9000P%202021H){:target="_blank"} for your device display (Control Panel/Color management)
- (optional) Install these custom calibrated profiles
  - [Custom Legion 5 Pro / Legion 7 (AMD)](https://laptopwiki.eu/wp-content/uploads/2021/11/Legion_5_Pro.icm_.zip){:target="_blank"}
  - [Custom Legion 5 (21) 165Hz (AMD)](https://drive.google.com/file/d/1zDYmPAPtJv65NMO0AIRitGUFCZZG3GbO/view?usp=sharing){:target="_blank"}
  - [Legion 7i (Intel)](https://pixeldrain.com/u/BeLREnei){:target="_blank"}
- Install the [Nahimic app](https://www.microsoft.com/en-us/p/nahimic/9n36ppmp8s23?activetab=pivot:overviewtab){:target="_blank"} for improving the sound

- (Optional) Install the recommended Nvidia driver for your GPU from the Nvidia site, we don't recommend using Geforce Experience due to the issues it causes in many games (check [discord server](https://discord.com/channels/819491422327406592/938382715709968404/998990738308214894){:target="_blank"} for a recommended driver)
- Here is the archive with all the Legion 5 Pro drivers that are provided by Lenovo for the models delivered with Windows installed
  - [Legion 5 Pro / Legion 7 (AMD)](https://drive.google.com/file/d/1LKJRfnoEZwiY7F6Pnwy-LJ1sUcDZHEzg/view?usp=sharing){:target="_blank"}
  - [Legion 5i Pro (Intel)](https://drive.google.com/file/d/1zDYmPAPtJv65NMO0AIRitGUFCZZG3GbO/view?usp=sharing){:target="_blank"}
  - [Legion 7i (Intel)](https://pixeldrain.com/u/BeLREnei){:target="_blank"}


Now enjoy your no OS Legion with Legion experience as others!
