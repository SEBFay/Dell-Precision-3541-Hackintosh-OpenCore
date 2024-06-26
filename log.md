- This log file starts at 12-31-2022. Any previous changes to the EFI file and its configurations will be reflected in the previous commits.
- This log file will be in English.
- 这个日志文件于2022年12月31日开始更新。在此之前对EFI文件及其配置的更改信息请参阅之前的commits。
- 这个日志文件将用英语编写。

- Date Format / 日期格式: MM-dd-YYYY


## 12-31-2022：
- ACPI：Disabled SSDT-PLUG-DRTNIA.aml in config.plist but retained the file in ACPI folder 
- - macOS 13.1 does not require this for power management/thermal control.
- Kernel: Added in SD card slot related kexts from https://github.com/0xFireWolf/RealtekCardReader, but disabled 
- - will be working on SD card slot soon.

## 02-09-2023：
- OpenCore: Updated to 0.8.8
- ACPI: Included disable dGPU hotpatch - still testing to see if work and helps battery performance
- Kexts: Included CPUFriend, Realtek Card Reader; Updated Airportitlwm
- Added boot-arg "io80211.awdl=0" for better Wi-Fi performance post-boot/wake
- Tested compatible with macOS 13.2

## 03-18-2023：
- OpenCore: Updated to 0.9.0
- Kexts: Disabled Intel related network kexts as the adapter has been changed to BCM94360NG & added corresponding kexts for the adapter.
- boot-arg: Removed "io80211.awdl=0"
- Audio layout-id: Changed to 15 for better combojack output
- With something else that I did not make notes.
- Tested compatible with macOS 13.2.1

## 06-05-2023：
- OpenCore: Updated to 0.9.2
- Kexts: Updated some of them.
- readme: Reconstructed and added more info.
- Tested compatible with macOS 13.4 with minor issues.

## 10-09-2023:
- Updated readme.md & readme_chs.md with grammar/spelling check.
- Tested compatible with macOS 13.6.
- Will be working on ThunderBolt 3 hotplug & video/audio output.

## 03-09-2024:
- OpenCore: Updated to 0.9.8
- Kexts: Updated some of them, deleted Intel Wireless related ones and unused Voodoo PS2 controllers
- config: Added support for macOS Sonoma WiFi, Disabled SIP for post-install/upgrade OCLP Patch
- bootarg: -igfxblr replaced by -igfxblt, added -igfxbls for smooth brightness control. See： [WhateverGreen](https://github.com/acidanthera/WhateverGreen?tab=readme-ov-file#global)
- Tested compatible with macOS 14.4

## 03-29-2024:
- OpenCOre: Updated to 0.9.9
- Kexts: Updated some of them, deleted IntelSnowMausi.kext
- Changed SMBIOS to MacBookPro16,3 for Type-C to DP