# __未完成__ - macOS Ventura 13.2 - Dell Precision 3451

## 配置:

- CPU: Intel i7-9750H
- 音频编码: Intel ALC236/3204
- 网卡: Intel AC9560 + 蓝牙
- 显卡: Intel UHD 630 + ~~nVidia Quadro P620~~

## 现在可以正常使用的功能:

- 电量信息
- Fn键盘背光调节
- Fn音量调节
- Fn亮度调节
- 带手势的触摸板 + 指点杆
- 无线网 (使用Airportitlwm)
- 蓝牙
- USB接口
- MicroSD 卡槽
- 声卡驱动（内置输入/输出）- ALC236/3204
- 耳机孔输出 - 需要将输出平衡调节至极左或极右

## 现在没发现问题/不能正常使用的功能:

- 隔空投送，随航 和其他Intel网卡驱动不支持的功能
- HDMI输出 - 接口直连被屏蔽的独立显卡
- 关于计算器功能的小键盘快捷键
- 雷电3
- 耳机孔输入
- 一些在itlwm 0.2.2中提到的关于Ventura的问题
- 还有很多我没有测试的 - 或许可以正常使用

## 备注:

因为暂时没有Type-C USB3.0设备，雷电3接口现在只能运行在USB2.0速率。

在打过SSDT热补丁来禁用独立显卡之后，续航依旧很糟糕。正在寻找解决办法。

个人认为最合适的仿冒型号是MacBookPro16,4。

在config.plist中，序列号和其他特殊信息被设定为0 - 请在使用前生成数据并修改文件。

这个项目还没完全完善，并且我没有测试过高强度/日常使用的稳定性能。

使用时风险自负，我只能保证在安装和进入macOS时，这套EFI文件能给您提供基本功能。


## 参考:

- 官方OpenCore安装指南 --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
- 黑果小兵 - OC-little --> https://github.com/daliansky/OC-little
- OpenIntelWireless - itlwm --> https://github.com/OpenIntelWireless/itlwm