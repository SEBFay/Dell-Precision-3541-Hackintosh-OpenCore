- This log file starts at 12-31-2022. Any previous changes to the EFI file and its configurations will be reflected in the previous commits.
- This log file will be in English.
- 这个日志文件于2022年12月31日开始更新。在此之前对EFI文件及其配置的更改信息请参阅之前的commits。
- 这个日志文件将用英语编写。

# Changes made:

12-31-2022：
- ACPI：Disabled SSDT-PLUG-DRTNIA.aml in config.plist but retained the file in ACPI folder 
- - macOS 13.1 does not require this for power management/thermal control.
- Kernel: Added in SD card slot related kexts from https://github.com/0xFireWolf/RealtekCardReader, but disabled 
- - will be working on SD card slot soon.

02-09-2023：
- OpenCore: Updated to 0.8.8
- ACPI: Included disable dGPU hotpatch - still testing to see if work and helps battery performance
- Kexts: Included CPUFriend, Realtek Card Reader; Updated Airportitlwm
- Added boot-arg "io80211.awdl=0" for better Wi-Fi performance post-boot/wake
- Tested compatible with macOS 13.2