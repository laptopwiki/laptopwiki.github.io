---
layout: wiki
title: Re-Flashing Guide
description: "Detailed Guide to Re-flashing a soft-bricked GPU"
parent: Performance, Thermal and Fan Management
grand_parent: General
contributors:
discord: ['aaalbert#1784'] 
---

# Re-flashing a soft-bricked GPU

Accidentally bricked your Legion's GPU after flashing a VBIOS? Don't worry, there's a way to make your laptop functional again. A soft-bricked GPU will display a black screen upon boot. To fix this, follow the following steps 

- Firstly, boot into safe-mode. Prepare a bootable USB with Windows Installation Media. Spam **F12** after powering on the laptop, you will be presented with a screen asking you to select a boot drive. Select your bootable USB and proceed with Windows Setup.

- Press Next

{: .center}
![image](https://cdn.discordapp.com/attachments/840314972918644767/906344226214805504/img_1.png)

- Press **Repair your computer**

{: .center}
![image](https://cdn.discordapp.com/attachments/840314972918644767/906344284633059328/img_2.png)

- Select `Startup Settings` and press `Restart`. After restarting press `F4` to boot into **safe mode**. If Startup Settings isn't there, select Command Prompt and then type `bcdedit /set {default} safeboot minimal` in Command Prompt.

{: .center}
![image](https://cdn.discordapp.com/attachments/840314972918644767/906344391646539776/img_3.jpg)

- Exit Command Prompt and proceed to Windows. Use the attached NVFlash (patched for Ampere mobile) to re-flash your orginial VBIOS. This patched version bypasses all Board ID Mismatch errors.

⋅⋅⋅1. Open a Command Prompt as Administrator.
⋅⋅⋅2. **cd..** to the location of your NVFlash folder.
⋅⋅⋅3. Run **nvflash_patched_ampere -6 *insert original VBIOS name.rom*** Very Important: This only works on Nvidia RTX 3000 series mobile GPUs, as mentioned in the title (may work in other GPUs such as AMD if you already have the stock rom file)