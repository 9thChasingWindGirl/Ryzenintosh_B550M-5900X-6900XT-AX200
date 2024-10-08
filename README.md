  # OPENCORE 版本 1.0.1
## 转换语言
- **简体中文**
- [English](/README_EN.md)
## 硬件情况
* 主板：华硕 TUF GAMING B550M-ZAKU (WI-FI)
* 处理器：AMD Ryzen9 5900X
* 显卡：AMD Radeon™ RX 6900 XT 16G TOXIC 毒药 OC 限量版
* 内存条：七彩虹 8GB ddr4 3200 X4
* 无线网卡：板载英特尔AX200

-------

> 目前运行系统版本：macOS Sonoma 14.6.1

![image](/sysinfo.jpg)

-------

![image](/desktop.png)

## 引导说明
### 电源管理（ACPI）
* SSDT-CPUR.aml
* SSDT-EC-USBX.aml
* SSDT-SBUS-MCHC.aml
* SSDT-PLUG_RYZEN.aml
### 设备属性（DP/deviceproperties）
* 有线网卡内建（不同主板需要修改pci设备地址，嫌麻烦可以删除）：PciRoot(0x0)/Pci(0x1,0x2)/Pci(0x0,0x2)/Pci(0x9,0x0)/Pci(0x0,0x0)
* 无线网卡内建（不同主板需要修改pci设备地址，嫌麻烦可以删除）：PciRoot(0x0)/Pci(0x1,0x2)/Pci(0x0,0x2)/Pci(0x8,0x0)/Pci(0x0,0x0)
* 6900xt注入参数（可能需要修改pci设备地址，嫌麻烦可以删除）：PciRoot(0x0)/Pci(0x3,0x1)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)
### 内核驱动（Kernel）
1. Lilu.kext
2. VirtualSMC.kext
3. AppleMCEReporterDisabler.kext
4. ~~WhateverGreen.kext~~ NootRX.kext *！
5. AppleALC.kext
6. - [ ] AirportItlwm.kext
   - [x] itlwm.kext *！[由于iMessage 和相关服务无法与 AirportItlwm.kext 协同工作，请改用 itlwm.kext 或内置 NIC 作为主要设备](https://github.com/OpenIntelWireless/itlwm/releases/tag/v2.3.0)
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
17. SMCAMDProcessor.kext
18. SMCSuperIO.kext
19. SMCRadeonSensors.kext *！
20. USBPorts.kext
21. XHCI-unsupported.kext

# *！*：
1. AMDRyzenCPUPowerManagement.kext和SMCAMDProcessor.kext配合[AMD.Power.Gadget.app](https://github.com/trulyspinach/SMCAMDProcessor/releases)使用；
2. SMCRadeonSensors.kext配合[stats.app](https://github.com/exelban/stats/releases)使用； 
3. AirportItlwm.kext替换为itlwm.kext，需要搭配[HeliPort.app](https://github.com/OpenIntelWireless/HeliPort/releases)使用

#### 内核驱动-补丁（Kernel-Patch）
“algrey - Force cpuid_cores_per_package”开头的四个条目已修改为5900X；
PAT patch方式在该引导文件中使用Shaneee的补丁（解决infuse低帧率）
[内核补丁及使用方式](https://github.com/AMD-OSX/AMD_Vanilla)

### 杂项（Misc）
引导文件中“configo.plist”为去掉跑码和opencore选单，“configv.plist”为跑码和显示opencore选单（30秒超时）；

**！：** 初次使用建议使用“configv.plist”（**更名“configv.plist”为“config.plist”**）

### 机型（Platforminfo）
自行更改所需机型，并生成三码。

## 使用情况
1. 睡眠未开启；
2. 无法使用隔空投送；
3. ~~蓝牙文件传送无法使用；~~
4. 连续互通相机需有线连接。

# 更新的引导文件在[Release](https://github.com/9thChasingWindGirl/Ryzenintosh_B550M-5900X-6900XT-AX200/releases)下载

## 相关链接
1. [https://dortania.github.io/getting-started/（opencore官方指导）](https://dortania.github.io/getting-started/)
2. [https://apple.sqlsec.com/ （国光黑苹果）](https://apple.sqlsec.com/)
3. [https://space.bilibili.com/16323318?spm_id_from=333.337.0.0 （大头蔡Cass）](https://space.bilibili.com/16323318?spm_id_from=333.337.0.0)
4. [https://www.youtube.com/@casstsai （大头蔡Cass）](https://www.youtube.com/@casstsai)

