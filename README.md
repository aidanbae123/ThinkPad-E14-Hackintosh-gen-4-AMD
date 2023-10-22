# Hackintosh-ThinkPad-E14-Gen-4-AMD

This is a mostly functioning EFI for the ThinkPad E14 gen 4 (AMD version).
DISCLAIMER: This is a work in progress, so I am not responsible for any damage that may occur to your computer. Use at your own risk.

Specs:

- Ryzen 7 5825U 
- Vega 8 iGPU
- 16GB DDR4-3200 SODIMM RAM (8GB Soldered + 8GB SODIMM)
- NVME SSDs: 
    256GB (Windows) + 512GB (Opencore)
- RTL8852BE (unsupported)
- RTL8188 (Ethernet)
- ALC3287/257


Working:

- iGPU + Hardware Accelration (via NootedRed)
- Ethernet
- Camera
- Keyboard, Trackpad, and Trackpoint
- Audio (Mostly)
- Dual Boot
- WiFi + BT (via USB dongles):
    - WiFi: RTL8188CU
    - BT: TP-Link UB400
    
What doesn't work:

- Native Wifi + BT (unsupported)
- Airplay, Sidecar, etc.
- Internal Mic
- Sleep (Very inconsistent)
- en0 (iServices via WiFi)
- Chrome and Firefox (Requires hardware acceleration to be disabled)

