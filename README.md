# OPENCORE 版本 0.9.0
## 硬件情况
* 主板：华硕 TUF GAMING B550M-ZAKU (WI-FI)
* 处理器：AMD Ryzen9 5900X
* 显卡：撼讯 AMD 5700XT
* 内存条：七彩虹 8GB ddr4 3200 X4
* 无线网卡：板载英特尔AX200

-------

> 目前运行系统版本：macOS Ventura 13.3

-------

![](https://github.com/YUANJIANGWANGYU/Ryzenintosh_B550M-5900X-5700XT-AX200/blob/main/screenshot2023-03-30 23.10.37.webp)

## 引导说明
### 电源管理（ACPI）
* SSDT-CPUR.aml
* SSDT-EC-USBX.aml
* SSDT-SBUS-MCHC.aml
### 设备属性（DP/deviceproperties）
* 有线网卡内建（不同主板需要修改pci设备地址，嫌麻烦可以删除）：PciRoot(0x0)/Pci(0x1,0x2)/Pci(0x0,0x2)/Pci(0x3,0x0)/Pci(0x0,0x0)
* 5700xt仿冒W5700X（可能需要修改pci设备地址，嫌麻烦可以删除）：PciRoot(0x0)/Pci(0x3,0x1)/Pci(0x0,0x0)/Pci(0x0,0x0)/Pci(0x0,0x0)
### 内核驱动（Kernel）
1. Lilu.kext
2. VirtualSMC.kext
3. AppleMCEReporterDisabler.kext
4. WhateverGreen.kext
5. AppleALC.kext
6. BlueToolFixup.kext
7. IntelBluetoothFirmware.kext
8. IntelBTPatcher.kext
9. AirportItlwm.kext
10. RTCMemoryFixup.kext
11. RestrictEvents.kext
12. NVMeFix.kext
13. LucyRTL8125Ethernet.kext
14. HibernationFixup.kext
15. AMDRyzenCPUPowerManagement.kext *！
16. SMCAMDProcessor.kext *！
17. RadeonSensor.kext *！
18. SMCRadeonGPU.kext *！

# *！*：
1. AMDRyzenCPUPowerManagement.kext和SMCAMDProcessor.kext配合[AMD.Power.Gadget.app](https://github.com/trulyspinach/SMCAMDProcessor/releases/download/0.7.1/AMD.Power.Gadget.app.zip)使用；
2. RadeonSensor.kext和SMCRadeonGPU.kext配合[RadeonGadget.app](https://github.com/aluveitie/RadeonSensor/releases/download/0.3.3/RadeonSensor-0.3.3.zip)使用。

#### 内核驱动-补丁（Kernel-Patch）
“algrey - Force cpuid_cores_per_package”开头的四个条目已修改为5900X；
PAT patch方式在该引导文件中使用Shaneee的补丁（解决infuse低帧率）
[内核补丁及使用方式](https://github.com/AMD-OSX/AMD_Vanilla)

### 杂项（Misc）
引导文件中“configooo.plist”为去掉跑码和opencore选单，“configvp.plist”为跑码和显示opencore选单（30秒超时）；
**！：** 初次使用建议使用“configvp.plist”（**更名“configvp.plist”为“config.plist”**）

### 机型（Platforminfo）
自行更改所需机型，并生成三码。

## 使用情况
1. 睡眠未开启；
2. 无法使用隔空投送；
3. 蓝牙文件传送无法使用；
4. 连续互通相机需有线连接。

# 更新的引导文件在Release下载

## 相关链接
1. [https://dortania.github.io/getting-started/（opencore官方指导）](https://dortania.github.io/getting-started/)
2. [https://apple.sqlsec.com/ 国光黑苹果](https://apple.sqlsec.com/)


