# Hackintosh EFI for Gen 4 AMD ThinkPad E14

Opencore version v1.0.3

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
- macOS Ventura 13.7.2 (22H313)

## Working:

- iGPU + Some Hardware Accelration (via NootedRed)
- Ethernet
- Webcam
- Keyboard, Trackpad, and Trackpoint
- Audio
- Built-in mic
- Dual Boot
- Continuity Camera (Wired ONLY)
- SLEEP - Now thanks to using USBMap.kext rather than USBToolBox.kext

## Minor issues:
- Battery life is quite poor
- Facetime is weird: There is no incoming video on calls (other person can see you but you can't see them). Audio works fine.
- ~~Audio stops working every now and then, but can be fixed by opening settings and re-selecting the internal speakers as output~~ Now seemingly gone with appleALC updates
~~- Certain OpenGL apps (such as Chrome) cause massive glitches. Unfortunately not much can be done about this as it is an issue with NootedRed itself.~~ Can now be fixed using [AMDHelper]([url](https://github.com/alvindimas05/AMDHelper))- experimental but seems to work fine.
- Settings sometime crashes (Fixed by running "sudo purge" in terminal)
- Sonoma is still quite buggy
- When you have too much storage used, the laptop starts restarting with an "NVME command timeout" kernel panic
    
## What will never work with my specs:
- Airplay, Sidecar, etc. (Airport needs an authentic apple WiFi chip & sidecar is intel-ONLY)
  
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

- IMPORTANT: Intall [AMDHelper](https://github.com/alvindimas05/AMDHelper) to patch any chromium/openGL based apps to prevent severe compute crashes.
- Recommended: Set VRAM to 2GB (or 4GB) in BIOS for improved graphics performance
    - This option is under Config/Display in the ThinkPad BIOS
- Optional: Change CPU name to actual CPU using @corpnewt's [CPU-name](https://github.com/corpnewt/CPU-Name)


