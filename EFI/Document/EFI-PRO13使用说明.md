# EFI-PRO13-AOAC

## 适用

- 联想小新 `2019 PRO13` 、 `2019 PRO13S` 、 `2020 PRO13` 

## 使用说明

#### 设置BIOS【[CLCN32WW.DPC10 / 小新PRO13修改DVMT说明](https://github.com/daliansky/XiaoXinPro-13-hackintosh/tree/master/EFI/files)】
注意：刷BIOS有风险

- **解锁**  `DVMT` 、`CFG` 
  - `DVMT` =64M；位置：Advanced -> System Agent -> Graphics Configura -> DVMT Pre-Allocated
  - `CFG` =disable；位置：Advanced -> Power Performanc -> CPU Power  Manage -> CPU Lock Configura
- **Security** 【**重要**】
  - `Intel Platform Trust Technology` = `Disable` 
  - `Intel SGX Control` = `Disable` 【**建议**】
  - `Secure Boot` = `Disable` 
- **其他** 【**小新PRO13修改DVMT说明**】


## OpenCore版本
- OC releases：https://github.com/acidanthera/OpenCorePkg/releases
## Clover版本
- Clover releases：https://github.com/CloverHackyColor/CloverBootloader/releases

## 常用kexts下载地址
  - https://github.com/acidanthera  

  - Lilu: https://github.com/acidanthera/Lilu/releases  
  - WhateverGreen: https://github.com/acidanthera/WhateverGreen/releases  
  - VirtualSMC: https://github.com/acidanthera/VirtualSMC/releases  
  - VoodooI2C: https://github.com/VoodooI2C/VoodooI2C/releases  
  - AppleALC: https://github.com/acidanthera/AppleALC/releases  

  - Intel 网卡:  https://github.com/OpenIntelWireless  

  - 常用Kexts：https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Kexts.md  

  - ***睡眠APP-SleeperX***：https://github.com/HsOjo/SleeperX/releases

## 参考内容

- OpenCore官方文档
- OC-little：https://github.com/daliansky/OC-little ，特别是其中的《关于AOAC》部分  
- @Donald 的《修改DVMT Pre-Allocated数值方法》
- @OC-xlivans的《OC-引导多系统@OC-xlivans》
- @Dreamn的《睡眠自动关闭蓝牙WIFI》

#### 配置config

- `PlatformInfo` 
  - 参考OC官方文件 `Sample.plist` 或者 `SampleCustom.plist` 配置机型数据
- `DeviceProperties` 
  - 根据自己的情况调整 `AAPL,ig-platform-id` 、`device-id` 
- `NVRAM\Add\7C436110-AB2A-4BBB-A880-FE41995C9F82\boot-args` 
  - 根据自己的情况调整 `alcid` ，如： `alcid=11` 、`alcid=18` 、`alcid=86` 、`alcid=99` 、 `alcid=100` 

#### 网卡驱动及驱动列表

- 白果卡【带转接板】无需驱动

- 博通系列网卡，如1820A等需以下驱动。驱动列表参考《config-BCM无线和蓝牙驱动列表》
  - 蓝牙：https://github.com/acidanthera/BrcmPatchRAM
  - Wi-Fi：https://github.com/acidanthera/AirportBrcmFixup
- Intel系列网卡需以下驱动。驱动列表参考《config-Intel无线和蓝牙驱动列表》
  - 蓝牙：https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases
  - Wi-Fi：https://github.com/OpenIntelWireless/itlwm

#### 使用 EFI

- 引导界面会显示MAC、Windows引导和 Shutdown，其它内容被隐藏。按下空格键弹出其它菜单。
- 第一次使用本 EFI、更改EFI内容、以及更新系统时，按下空格键后执行 `CleanNvram` 、 `NvramReset` 。

## 其他

- 关闭触摸板快捷键
  - 组合键： `FN+F6` 
- 唤醒方法
  - **电源键** 
- 已知问题
  - 内置MIC不工作

## 注意事项

- 请使用 ***Xcode***、***Propertree***、***PlistEdit Pro*** 等工具编辑config.plist。
- 如果你不了解 **OpenCore Configurator.app** 和 OC 版本之间的关系时，请不要使用它。不正确的操作方法会破坏 config 文件数据结构。但可以通过它获取机型数据。
- 对盒盖电源状态有特殊要求的请使用 ***SleeperX*** ，见《OC及常用kexts下载地址》的 ***睡眠APP-SleeperX*** 。

## 更多请看：[wiki](https://github.com/daliansky/XiaoXinPro-13-hackintosh/wiki)