# __Work In Progress__ - macOS Ventura 13.1 - Dell Precision 3451

中文Readme请点击 --> [README_CHS.md](https://github.com/SEBFay/Dell-Precision-3541-Hackintosh-OpenCore/blob/main/README_CHS.md)

![Dell Precision 3451](https://www.bhphotovideo.com/images/images1500x1500/dell_sbr57_precision_3541_i7_9850h_16gb_1538045.jpg)

## Specs:

- CPU: Intel i7-9750H
- Audio Codec: Intel ALC236/3204
- Network Adapter: Intel AC9560 + Bluetooth
- GPU: Intel UHD 630 + ~~nVidia Quadro P620~~

## What works for now, as I have discovered so far:

- Battery Status
- Audio Input/Output - ALC236/3204
- Backlight Fn Keys
- Audio Fn keys
- Trackpad with Gestures + TrackPoint
- Wi-Fi (Airportitlwm)
- Bluetooth
- Headphone Jack - Need to tune the output balance to extreme left or right

## What doesn't work & not tested:

- Brightness Fn keys - Working in Progress
- USB hubs - Working in Progress
- AirDrop, SideCar, etc. - Limited by Intel Network Adapter
- Micro SD slot
- Sleep/Wake when lid Closed/Open (Unsure)
- Power Management (Unsure)
- Numpad Calculator related hotkeys
- Many more which either works but I haven't found out or simply doesn't work

## Notes:

The fan goes quite hard for most of the time, but it does change the speed based on the temperature of the laptop. This might be related to EC thermal management on my unit as it was set to "Optimal"

Personally, I think the most suitable model for the system to identify the laptop is MacBookPro16,4.

Serial Numbers and other unique information are being set to 0 in config.plist - Please generate the info and change the data before use.

I haven't tested if it's suitable to be in your daily driver, and of course, the whole thing is "work in progress"

Use at your own risk, as this set of EFI file only allows you to install, boot into macOS with basic functions. 

## References:

- OpenCore --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
