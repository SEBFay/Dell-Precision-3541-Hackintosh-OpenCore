# __Work In Progress__ - macOS Ventura 13.4 - Dell Precision 3451

中文Readme请点击 --> [README_CHS.md](https://github.com/SEBFay/Dell-Precision-3541-Hackintosh-OpenCore/blob/main/README_CHS.md)

<img decoding="async" src="https://raw.githubusercontent.com/SEBFay/Dell-Precision-3541-Hackintosh-OpenCore/main/screenshots/3541hac.png" width="75%" class="aligncenter">

## Specs:

- OpenCore version: 0.9.2
- CPU: Intel i7-9750H
- Audio Codec: Intel ALC236/3204
- Network Adapter: ~~Intel AC9560 + Bluetooth~~ / BCM94360NG
- GPU: Intel UHD 630 + ~~nVidia Quadro P620~~

## What works with no issues:

- Battery Status
- Fn Keys (Brightness, Audio, Keyboard backlight)
- Trackpad with Gestures + TrackPoint
- Wi-Fi + Bluetooth
- USB ports (limited support)
- Audio onboard Input/Output
- Combo Jack output
- AirDrop, Handoff, Sidecar & other iService functions

## What doesn't work:

- HDMI Output - Impossible, as the port is connected to eGPU
- Numpad Calculator related hotkeys
- ThunderBolt 3 with video/audio output
- Combo Jack audio input
- MicroSD Card reader
- Many more which either works but I haven't found out or simply doesn't work

## What works, but with issues: 

I do not have any USB3.0 Type-C devices ATM, so the ThunderBolt 3 port only runs at USB2.0 for now.
- The USB mapping is still TBD, with TB3 video output fixings on the plan.

After bootup, the screen brightness is broken (Extremely low) for a couple of minutes and will light up again.
- bootargs: -igfxblr is not working due to some Apple-end issues for Ventura 13.4. See: https://github.com/acidanthera/bugtracker/issues/2241

Trackpad sometimes doesn't listen to you - I suggest to disable "Tap to Click" and solely use the left/right button below or above the trackpad.
- For me, it will ghost click and ruin my day.

Battery life is still very bad after having eGPU disabled with SSDT hotpatch and in bootargs. 
- Maybe it's just my battery. Please test at your end and give feedback.

Overall temperature when running is mostly 90°C+ when plugged in for the first few continuous hours, then will reduce to 40-60°C when it wants to.
- CPU clock would be capped at 0.8 GHz at random and unexpected moments for am unknown period when its at 90°C+ and the whole thing goes unresponsive.

## Notes:

I kept the files but disabled the intel wifi adapter related kexts. If needed, you can disable the broadcom related kexts and re-enable the intel ones.

Serial Numbers and other unique information are being set to 0 in config.plist - Please generate the info and change the data before use for iServices.

The whole setup is enough for me as a daily driver, but might not be the case for you - Use at your own risk, as this set of EFI file allows you to install, boot into macOS with normal functions. 

## Disclamers:

I'm not responsible for any bricked devices, dead hard drives, Special Military Operation, or your project getting delayed because the whole thing won't boot up.
YOU are choosing to make these modifications with my setup, and if you point the finger at me for messing up your device with my EFI setup, I will pray for you being dumb.
Your Apple ID might be restricted by Apple, there's nothing to do with me.
Your warranty might be void when you have already fiddled with your device. If the whole laptop dies, bad luck with you.

## References:

- OpenCore --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
- Daliansky - OC-little (Translated by 5T33Z0) --> https://github.com/5T33Z0/OC-Little-Translated
- OpenIntelWireless - itlwm --> https://github.com/OpenIntelWireless/itlwm
