# OPENCORE Version 0.9.5
## Language
- [简体中文](/README.md)
- **English**
## Hardware Info
* Motherboard：ASUS TUF GAMING B550M-ZAKU (WI-FI)
* CPU：AMD Ryzen9 5900X
* GPU：~~POWERColor AMD 5700XT~~ TOXIC AMD Radeon™ RX 6900 XT Limited Edition
* RAM：COLORFUL 8GB ddr4 3200 X4
* Wireless：Intel AX200 onboard

-------

> Currently System Version：macOS Sonoma 14.0

![image](/38dab3785f76a621c704c856d8cad66.jpg)

-------

![image](/2023-10-21%2017.18.46.png)


## EFI Notes
### ACPI
* SSDT-CPUR.aml
* SSDT-EC-USBX.aml
* SSDT-SBUS-MCHC.aml
* SSDT-PLUG_RYZEN.aml
### DP/deviceproperties
* Ethernet Built-in（Different motherboards need to modify the pci device address, which can be deleted if it is troublesome）：PciRoot(0x0)/Pci(0x1,0x2)/Pci(0x0,0x2)/Pci(0x9,0x0)/Pci(0x0,0x0)
* Wi-fI Built-in（Different motherboards need to modify the pci device address, which can be deleted if it is troublesome）：PciRoot(0x0)/Pci(0x1,0x2)/Pci(0x0,0x2)/Pci(0x8,0x0)/Pci(0x0,0x0)
* 6900xt dpinfo-inject（Necessary to modify the address of the pci device, but it can be deleted if it is troublesome）：
PciRoot(0x0)/Pci(0x3,0x1)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)
### Kernel
1. Lilu.kext
2. VirtualSMC.kext
3. AppleMCEReporterDisabler.kext
4. ~~WhateverGreen.kext~~ NootRX.kext *！
5. AppleALC.kext
6. AirportItlwm.kext
7. BlueToolFixup.kext
8. IntelBluetoothFirmware.kext
9. IntelBTPatcher.kext
10. RTCMemoryFixup.kext
11. RestrictEvents.kext
12. Innie.kext
13. NVMeFix.kext
14. LucyRTL8125Ethernet.kext
15. HibernationFixup.kext
16. AMDRyzenCPUPowerManagement.kext *！
17. ~~SMCAMDProcessor.kext~~
18. SMCSuperIO.kext
19. SMCRadeonGPU.kext *！
20. RadeonSensor.kext *！
21. USBPorts.kext
22. XHCI-unsupported.kext

# *！*：
1. AMDRyzenCPUPowerManagement.kext、~~SMCAMDProcessor.kext~~、[AMD.Power.Gadget.app](https://github.com/trulyspinach/SMCAMDProcessor/releases/download/0.7.1/AMD.Power.Gadget.app.zip) need to be used together；
2. RadeonSensor.kext、SMCRadeonGPU.kext、[RadeonGadget.app](https://github.com/aluveitie/RadeonSensor/releases/download/0.3.3/RadeonSensor-0.3.3.zip) need to be used together.

#### Kernel-Patch
Beginning with “algrey - Force cpuid_cores_per_package” had been modified to 5900X；
PAT patch method uses Shaneee's patch in this EFI file（to solve the low frame rate of infuse.app）
[Kernel Patch And Usage(AMD_Vanilla)](https://github.com/AMD-OSX/AMD_Vanilla)

### Misc
The file “configo.plist” removes "-v" and OpenCore menus,“configv.plist” for showing.（30s timeout）；
**！：** Recommended for initial use “configv.plist”（**rename “configv.plist” to “config.plist”**）

### Platforminfo
Change the product model name you need and generate seria number.

## Usage
1. Sleep is not turned on；
2. Unable to use Airplay；
3. ~~Bluetooth cannot transfer files；~~
4. Continuous intercommunication cameras require wired connection.

# The updated EFI file is downloaded in [Release](https://github.com/YUANJIANGWANGYU/Ryzenintosh_B550M-5900X-5700XT-AX200/releases)

## Related Links
1. [https://dortania.github.io/getting-started/（opencore官方指导）](https://dortania.github.io/getting-started/)
2. [https://apple.sqlsec.com/ （国光黑苹果）](https://apple.sqlsec.com/)
3. [https://space.bilibili.com/16323318?spm_id_from=333.337.0.0 （大头蔡Cass）](https://space.bilibili.com/16323318?spm_id_from=333.337.0.0)
4. [https://www.youtube.com/@casstsai （大头蔡Cass）](https://www.youtube.com/@casstsai)
