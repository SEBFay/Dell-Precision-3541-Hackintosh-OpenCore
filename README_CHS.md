# __未完成__ - macOS Ventura 13.1 - Dell Precision 3451

## 配置:

- CPU: Intel i7-9750H
- 音频编码: Intel ALC236/3204
- 网卡: Intel AC9560 + 蓝牙
- 显卡: Intel UHD 630 + ~~nVidia Quadro P620~~

## 现在可以正常使用的功能:

- 电量信息
- 声卡驱动（输入/输出） ALC236/3204
- 背光键盘 + Fn音量调节
- 带手势的触摸板 + 指点杆
- 无线网 (使用Airportitlwm)
- 蓝牙

## 现在没发现问题/不能正常使用的功能:

- Fn亮度调节
- 电源管理（不确定是否正常工作）
- 隔空投送，随航 和其他网卡驱动不支持的功能
- 盒盖睡眠 + 开盖唤醒 （不确定）
- 还有很多我没有测试的 - 或许可以正常使用

## 备注:

个人认为最合适的仿冒型号是MacBookPro16,4。

在config.plist中，序列号和其他特殊信息被设定为0 - 请在使用前生成数据并修改文件。

因为这个项目还没完全完善，并且我没有测试过高强度/日常使用的稳定性能。

使用时风险自负，我只能保证在安装和进入macOS时，这套EFI文件能给您提供基本功能。


## 参考:

- 官方OpenCore安装指南 --> https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
- 国光的黑苹果安装教程 --> https://apple.sqlsec.com/
