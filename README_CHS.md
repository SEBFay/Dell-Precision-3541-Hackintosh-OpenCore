# macOS Sonoma 14.4 - Dell Precision 3451

## 配置:

- OpenCore版本： 0.9.9
- CPU: Intel i7-9750H
- 音频编码: Intel ALC236/3204
- 网卡: ~~Intel AC9560 + 蓝牙~~ / BCM94360NG
- 显卡: Intel UHD 630 + ~~nVidia Quadro P620~~
- 仿冒Mac型号：MacBookPro16,3

## 现在可以正常使用的功能:

- 电量信息
- Fn键盘背光，音量，屏幕亮度调节
- 带手势的触摸板 + 指点杆
- 无线网 + 蓝牙
- USB接口（有限制的支持）
- 声卡驱动（内置输入/输出）
- 耳机孔输出
- 隔空投送, 连续互通，随航等iService功能
- Apple Watch解锁
- Type-C输出DisplayPort信号

## 现在没发现问题/不能正常使用的功能:

- HDMI输出 - 已经确认接口连接的是核显，但是在试过所有bus-id后还是无法启用。若想使用外接屏幕，请使用Type-C转DP。
- 关于计算器功能的小键盘快捷键
- 耳机孔输入
- MicroSD 卡槽
- Apple Music和其他DRM视频/音频内容
- 还有很多我没有测试的 - 或许可以正常使用

## 现在可以使用，但有点问题的功能: 

因为暂时没有Type-C USB3.0设备，雷电3接口或许只能运行在USB2.0速率。
- 正在准备制作完整USB映射文件，包括修复雷电3接口的视频输出。

~~开机之后的几分钟内，屏幕亮度会被强制设定为最低且不能更改 - 过了几分钟之后会自动修复。~~
- ~~bootargs: -igfxblr 不适配Ventura 13.4。 参阅: [这里](https://github.com/acidanthera/bugtracker/issues/2241)。~~

背光问题已经解决，替换bootarg “-igfxblr"为“-igfxblt”即可。

触摸板有些时候会闹脾气 - 建议关闭“轻点来点按”，并只使用触摸板上下的两对鼠标按键。
- 对我而言，当打开“轻点来点按”功能时，它会鬼触，然后我就急了。

电池寿命一塌糊涂，甚至在打了SSDT热补丁和在bootargs里禁用独显之后依旧如此。
- 或许只是我的电池有毛病，请在你们的设备上测试并反馈。

设备温度在插电的时候可能会飙到90°C+，但连续使用未知长度的时间之后会降低并稳定在40-60°C。
- CPU频率会在设备温度90°C+的随机的时候被限制在0.8GHz一段时间，这段时间里整台电脑会很卡，然后你可能会急眼。
- 解决办法：清灰和换硅脂。

## 备注:

__当你发现你的蓝牙出问题的时候:（此处案例为BCM94360NG）__
1. 请尝试在“系统信息-蓝牙”中查找地址和固件版本，如果为null和v0 c0:
    - 在“系统信息-USB”中寻找“BRCM20702 Hub”，如果没有此项目：
        - 关机，拆去后盖，拔掉电池，长按电源键10秒，插回电池，开机。
2. 如果“系统信息-蓝牙”中的内容一切正常，“系统信息-USB”中也存在“BRCM20702 Hub”项，但依旧无法连接AirPods或其他设备：
    - 打开终端并输入“sudo purge”和/或“sudo pkill bluetoothd"。

~~我在文件中保留，但在config.plist里禁用了对英特尔网卡支持所需的kext文件。有需要可以将博通相关kext禁用后自行启用。~~  
在config.plist里已经删除英特尔网卡对应项。

在config.plist中，序列号和其他特殊信息被设定为0 - 请在使用前生成数据并修改文件。

这套EFI文件对于我自己来说是足够日常使用的，但对你来说可能不行。使用时风险自负，我只能保证在安装和进入macOS时，这套EFI文件能给你提供基本功能。

Apple Watch解锁在长时间休眠后或许会不可用 - 蓝牙模块会在解锁并进入桌面之后重启。

随机情况下它会内核恐慌 / 突然重启 / 重置BIOS - 尚不明确具体原因, 但正在寻找解决方案。

~~暂无计划开展对macOS Sonoma的支持。如果你想试着去用这套EFI文件去升级到Sonoma，请更新OpenCore版本和相对应的kext文件。更多信息 - 参阅：https://github.com/dortania/OpenCore-Legacy-Patcher/issues/1076~~  
现已支持macOS Sonoma。安装/升级后请参考 [EliteMacX86(英文)](https://elitemacx86.com/threads/how-to-fix-broadcom-wifi-on-macos-sonoma-and-later.1415/) 或者[cnblogs(中文)](https://www.cnblogs.com/wkvip/p/17787077.html) 来启用WiFi功能。

## 免责声明：

我对以下情况不负任何责任：电脑变砖、硬盘损毁、对乌特别军事行动、和因为你的电脑不能开机，你的老板/老师在项目延期的时候骂你。

是你选择使用我制作的EFI文件，当你的电脑因为这套文件出问题并指责我的时候，我会为你的智商祷告。

你的Apple ID可能会被苹果限制/封禁, 这与我无关。

当你决定或已经完成了对你的设备的捣鼓，你的保修可能会失效。如果你的电脑真的出了什么问题，只能说你先别急。

## 参考:

- 官方OpenCore安装指南 --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
- 黑果小兵 - OC-little --> https://github.com/daliansky/OC-little
- OpenIntelWireless - itlwm --> https://github.com/OpenIntelWireless/itlwm
