# Hackintosh EFI for Gen 4 AMD ThinkPad E14

Opencore version v0.9.9

This is a mostly functioning EFI for the ThinkPad E14 gen 4 (AMD version).

DISCLAIMER: This is a work in progress, so I am not responsible for any damage that may occur to your computer. Use at your own risk.
Also, it is generally recommended to build your own EFI, so use only as a last resort or as a guide.

* The current config.plist does NOT have a serial number. Download @corpnewt's GenSMBIOS to create one [here](https://github.com/corpnewt/GenSMBIOS).

** Do NOT include my Tools folder in your EFI folder. **

## My Specs:

- Ryzen 7 5825U 
- Vega 8 iGPU
- 16GB DDR4-3200 SODIMM RAM (8GB Soldered + 8GB SODIMM)
- NVME SSDs: 
    256GB (Windows) + 512GB (Opencore)
- Intel AX200
- RTL8188 (Ethernet)
- ALC3287/257
- macOS Ventura 13.6.5 (22G621)

## Working:

- iGPU + Hardware Accelration (via NootedRed)
- Ethernet
- Webcam
- Keyboard, Trackpad, and Trackpoint
- Audio
- Built-in mic
- Dual Boot
- Continuity Camera (Wired ONLY)

## Minor issues:
- Audio stops working every now and then, but can be fixed by opening settings and re-selecting the internal speakers as output
- Certain OpenGL apps (such as Notion) cause massive glitches. Unfortunately notm uch can be done about this as it is an issue with NootedRed itself.
- Sonoma is still quite buggy
    
## What doesn't work:

- ~~Sleep (Wakes to a black screen after a while)~~ Now seems to be somewhat functional thanks to either a DSDT patch OR [this supposed fix](https://www.tonymacx86.com/threads/solved-ventura-sonoma-random-scheduled-pm-wake-from-sleep.323359/)
- ~~Full EC Read-Write access for fan control~~ Now fixed thanks to @Collin8000
- ~~Internal Mic~~ PATCHED from AppleALC 1.8.8+

## What will never work with my specs:
- Airplay, Sidecar, etc. (Airport needs an authentic apple WiFi chip and sidecar is intel-ONLY)
  
## Installation instructions:

### Steps
1. Download the lastest package
2. Choose the config.plist that applies to you and delete the rest
3. Add your generated serial number, board number, etc. to the config.plist
4. RENAME THE FILE TO config.plist (no CAPS, or else it literaly won't boot)
5. Set BIOS settings
6. Add to EFI folder of USB installer (EFI/OC & EFI/BOOT)
7. Go through installation process
8. Apply post-install fixes

### Pre-install

- Before installing, you need to create your own SMBIOS via CorpNewt's genSMBIOS. The plist is configued to MacBookPro16,3, so generate serials according or use a different model (NOTE: MBP16,1 and 16,4 expect a dGPU and will cause issues with the iGPU).
- Make sure to (CMD + R) in propertree everytime you add any new files to the OC folder.
  

### Post-Install

- Recommended: Set VRAM to 2GB (or 4GB) in BIOS for improved graphics performance
    - If you have 8GB RAM, it is not recommended to upgrade to 4GB
    - This option is under Config/Display in the ThinkPad BIOS
- Recommended: Change CPU name to actual CPU using @corpnewt's [CPU-name](https://github.com/corpnewt/CPU-Name)


