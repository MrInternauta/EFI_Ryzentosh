# OpenCore 0.6.5 EFI for AMD Ryzen Hackintosh (macOS 10.13 - 11.0.1)
## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 7 3700X @ 3.6GHz 8-Core, 32MB |
| Motherboard | Gigabyte x570 UD |
| RAM | 32GB (2 x 16GB) RAM XPG GAMMIX D30 DDR4 @ 3200MHz |
| Audio Chipset | Realtek ALC887 |
| GPU | Sapphire RX 570 8GB GDDR5 |
| WiFi & Bluetooth | Fenvi T919 (BCM94360CD) |
| OS Disk (NVMe) | ADATA Xpg Sx6000 Pro 512GB |

**macOS version**: 11.0.1 (20B29)  
**OpenCore version**: 0.6.5  
## Table of content
 - [Compatible macOS versions](#Compatible-macOS-versions)
 - [Issues](#Issues)
 - [How to use](#How-to-use)
 - [Adobe applications fix](#Adobe-applications-fix)
 - [Guides](#Guides)
 - [Credits](#Credits)

## Compatible macOS versions
 - High Sierra (10.13.x)
 - Mojave (10.14.x)
 - Catalina (10.15.x)
 - Big Sur (11.x)

## Issues
 - Partially-working virtualization (only VirtualBox & Parallels Dekstop 13.1.0 or below)
 - Partially-working audio (Frontal and Back. USB microphone not)
 - OC: Failed to calculate size of false field containing <empty> as a type, context <Playchime> ! 

## How to use
  1. Make your USB installer with [**this guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
  2. Clone the repository and paste "BOOT" and "OC" directories into your's pendrive "EFI" folder
  3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select **Generate SMBIOS**, as the model select **iMacPro1,1**.
  4. Open config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree) and go to PlatformInfo > Generic. Set MLB (Board Serial), SystemSerialNumber (Serial) and SystemUUID (SmUUID) to generated values. Change ROM to your network card's MAC address without the `:` character. [**How to get MAC Address?**](https://www.wikihow.com/Find-the-MAC-Address-of-Your-Computer)
  5. Boot it!  

**You CAN NOT use SMBIOS from this repository, it MUST be unique for every macOS installation**

## Sleep informations
The SSDT is for my PC configuration, recomend get your own SSDT and debbug
To modify SSDT use [**MaciASL**](https://github.com/acidanthera/MaciASL). If SSDT does not help read [**Dortania's guide about sleep**](https://dortania.github.io/OpenCore-Post-Install/universal/sleep.html). Remember to try USB mapping.

## Adobe applications fix
Adobe applications crash on AMD Hackintoshes due to missing intel_fast_memset instructions. Follow [**this guide**](https://gist.github.com/mikigal/8e1f804fcd7dbafbded2f236653be7c8) to get it working!  

## Guides
**If you have any problems with installation or booting your macOS, kernel panics or another system related issue check OC configuration guide**  
**If something else isn't working properly (for example USB ports, iServices, DRM/Netflix) check Post-Install guide**
 - Creating USB installer: [**\*click\***](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
 - OpenCore configuration: [**\*click\***](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html)
 - Post-Install: [**\*click\***](https://dortania.github.io/OpenCore-Post-Install/)
 - Troubleshooting: [**\*click\***](https://dortania.github.io/OpenCore-Post-Install/)
 - ACPI patching: [**\*click\***](https://dortania.github.io/Getting-Started-With-ACPI/)
 - USB mapping: [**\*click\***](https://dortania.github.io/OpenCore-Post-Install/usb/)
## Credits
**Software:**
 - [[Bootloader] OpenCore](https://github.com/acidanthera/OpenCorePkg)
 - [[Patch] AMD_Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
 - [[Driver] OpenRuntime](https://github.com/acidanthera/OpenCorePkg)
 - [[Driver] OpenCanopy](https://github.com/acidanthera/OpenCorePkg)
 - [[Kext] Lilu](https://github.com/acidanthera/Lilu)
 - [[Kext] VirtualSMC](https://github.com/acidanthera/VirtualSMC)
 - [[Kext] WhateverGreen](https://github.com/acidanthera/WhateverGreen)
 - [[Kext] RealtekRTL8111](https://github.com/Mieze/RTL8111_driver_for_OS_X)
 - [[Kext] NVMeFix](https://github.com/acidanthera/NVMeFix)
 - [[Kext] AppleMCEReporterDisabler](https://github.com/AMD-OSX/AMD_Vanilla/blob/experimental-opencore/Extra/AppleMCEReporterDisabler.kext.zip)

 **People:**
 - [Apple](https://apple.com) for macOS
 - [AMD-OSX Developers](https://github.com/AMD-OSX) for kernel patches for AMD CPUs
 - [Acidanthera](https://github.com/acidanthera) for OpenCore and most of used kexts
 - [Mieze](https://github.com/Mieze) for RealtekRTL8111 kext
 - [Dortania](https://github.com/dortania) for OpenCore configuration guides
 - [XLNC](https://github.com/naveenkrdy) for Adobe patches for AMD CPUs
 - [AMD-OSX Community](https://amd-osx.com) for support while making my Hackintosh
- [[Readme.md] mikigal](https://github.com/mikigal/ryzen-hackintosh)  

<br>

![Screenshot](/screenshot.png?raw=true)
