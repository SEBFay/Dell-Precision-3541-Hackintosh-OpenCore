# __Work In Progress__ - macOS Ventura 13.2 - Dell Precision 3451

中文Readme请点击 --> [README_CHS.md](https://github.com/SEBFay/Dell-Precision-3541-Hackintosh-OpenCore/blob/main/README_CHS.md)

![Dell Precision 3451](https://www.bhphotovideo.com/images/images1500x1500/dell_sbr57_precision_3541_i7_9850h_16gb_1538045.jpg)

## Specs:

- CPU: Intel i7-9750H
- Audio Codec: Intel ALC236/3204
- Network Adapter: Intel AC9560 + Bluetooth
- GPU: Intel UHD 630 + ~~nVidia Quadro P620~~

## What works for now, as I have discovered so far:

- Battery Status
- Backlight Fn Keys
- Audio Fn keys
- Brightness Fn keys
- Trackpad with Gestures + TrackPoint
- Wi-Fi (Airportitlwm)
- Bluetooth
- USB hubs
- MicroSD Card reader
- Audio onboard Input/Output - ALC236/3204
- Combo Jack output - Need to tune the output balance to extreme left or right

## What doesn't work & not tested:

- AirDrop, SideCar, etc. - Limited by Intel Network Adapter
- HDMI Output - Impossible, as the port is connected to dGPU
- Numpad Calculator related hotkeys
- ThunderBolt 3
- Combo Jack audio input
- Some issues mentioned in itlwm for driver version 0.2.2 for Ventura
- Many more which either works but I haven't found out or simply doesn't work

## Notes:

I do not have any USB3.0 Type-C devices ATM, so the ThunderBolt 3 port only runs at USB2.0 for now.

Battery life is still very bad after having dGPU disabled with SSDT hotpatch. Still looking for solutions.

Personally, I think the most suitable model for the system to identify the laptop is MacBookPro16,4.

Serial Numbers and other unique information are being set to 0 in config.plist - Please generate the info and change the data before use.

I haven't tested if it's suitable to be in your daily driver, and of course, the whole thing is "work in progress"

Use at your own risk, as this set of EFI file only allows you to install, boot into macOS with basic functions. 

## References:

- OpenCore --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
- Daliansky - OC-little (Translated by 5T33Z0) --> https://github.com/5T33Z0/OC-Little-Translated
- OpenIntelWireless - itlwm --> https://github.com/OpenIntelWireless/itlwm