# __Work In Progress__ - macOS Ventura 13.1 - Dell Precision 3451

![Dell Precision 3451](https://www.bhphotovideo.com/images/images1500x1500/dell_sbr57_precision_3541_i7_9850h_16gb_1538045.jpg)

## Specs

- CPU: Intel i7-9750H
- Audio Codec: Intel ALC236/3204
- Network Adapter: Intel AC9560 + Bluetooth
- GPU: Intel UHD 630 + ~~nVidia Quadro P620~~

## What works for now, as I have discovered so far.

- Battery Status
- Audio ALC236/3204
- Keyboard with Backlight and Audio Fn keys
- Trackpad with Gestures
- Wi-Fi (Airportitlwm)
- Bluetooth

## What doesn't work & not tested.

- Brightness Fn keys
- Power Management
- AirDrop, SideCar, etc.
- Many more which either works but I haven't found out or simply doesn't work

## Notes

Serial Numbers and other informations are being set to 0 in config.plist - Please generate the info and change the data before use.

Use at your own risk, as this set of EFI file only allows you to install, boot into macOS with basic functions. 

I haven't tested if it's suitable to be in your daily driver, and of course, the whole thing is "work in progress"

## References:

- OpenCore --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
