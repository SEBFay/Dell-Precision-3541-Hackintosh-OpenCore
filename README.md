# __Work In Progress__ - macOS Ventura 13.2.1 - Dell Precision 3451

中文Readme请点击 --> [README_CHS.md](https://github.com/SEBFay/Dell-Precision-3541-Hackintosh-OpenCore/blob/main/README_CHS.md)

<img decoding="async" src="https://raw.githubusercontent.com/SEBFay/Dell-Precision-3541-Hackintosh-OpenCore/main/screenshots/3541hac.png" width="75%" class="aligncenter">

## Specs:

- OpenCore version: 0.9.0
- CPU: Intel i7-9750H
- Audio Codec: Intel ALC236/3204
- Network Adapter: ~~Intel AC9560 + Bluetooth~~ / BCM94360NG
- GPU: Intel UHD 630 + ~~nVidia Quadro P620~~

## What works for now, as I have discovered so far:

- Battery Status
- Fn Keys (Brightness, Audio, Keyboard backlight)
- Trackpad with Gestures + TrackPoint
- Wi-Fi + Bluetooth
- USB ports (limited support)
- Audio onboard Input/Output
- Combo Jack output

## What doesn't work & not tested:

- HDMI Output - Impossible, as the port is connected to dGPU
- Numpad Calculator related hotkeys
- ThunderBolt 3 with video/audio output
- Combo Jack audio input
- MicroSD Card reader
- Many more which either works but I haven't found out or simply doesn't work

## Notes:

I do not have any USB3.0 Type-C devices ATM, so the ThunderBolt 3 port only runs at USB2.0 for now.
 - The USB mapping is still TBD, with TB3 video output fixings on the plan.

Battery life is still very bad after having dGPU disabled with SSDT hotpatch. Maybe it's just my battery.

I kept but disabled the intel wifi adapter related kexts in the files. If needed, you can disable the broadcom related kexts and re-enable the intel ones.

Personally, I think the most suitable model for the system to identify the laptop is MacBookPro16,4.

Serial Numbers and other unique information are being set to 0 in config.plist - Please generate the info and change the data before use.

I haven't tested if it's suitable to be in your daily driver, and of course, the whole thing is "work in progress"

Use at your own risk, as this set of EFI file only allows you to install, boot into macOS with basic functions. 

## References:

- OpenCore --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
- Daliansky - OC-little (Translated by 5T33Z0) --> https://github.com/5T33Z0/OC-Little-Translated
- OpenIntelWireless - itlwm --> https://github.com/OpenIntelWireless/itlwm
