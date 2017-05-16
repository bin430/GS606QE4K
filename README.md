# GS606QE4K
针对微星GS60 6代黑苹果教程
感谢Rehabman，PMheart，darkhandz等大神。
参考了以下链接：
驱动+iasl工具：https://bitbucket.org/RehabMan/
4K补丁：https://github.com/PMheart/CoreDisplayFixup
6代i7本教程：https://github.com/darkhandz/XPS15-9550-OSX


![屏幕快照 2017-04-28 下午11.28.18](https://lh3.googleusercontent.com/-roVbFVDB6tg/WQNgTR8pYII/AAAAAAAAAuQ/hBEItcI1ij4clMsPmufAIqTVCpYOUsu9QCHM/I/%255BUNSET%255D)

1. Mac关机后重启问题：
在Clover-ACPI页面勾选FixShutdown
2. USB驱动
USB遮盖器：USBInjectAll.kext
3. BCM94352Z Wifi+蓝牙驱动![A8DDAC70-AE22-431A-874C-8A59A5CB2560](https://lh3.googleusercontent.com/-mtptiWBXyeE/WQNkJaSdQ_I/AAAAAAAAAug/fp8rXavNdiAsjk0HSNtcUg5u2zO_nz8kgCHM/I/A8DDAC70-AE22-431A-874C-8A59A5CB2560.png)

![屏幕快照 2017-04-29 上午12.03.57](https://lh3.googleusercontent.com/-h8t9sc_WNeA/WQNn-TiN8cI/AAAAAAAAAvA/qg9no4LphIIXfZi4VpgZRX4xquFJbPb_ACHM/I/%255BUNSET%255D)

wifi：
Kernel and Kext Patches：
FakePCIID_Broadcom_WiFi.kext
蓝牙：
BrcmFirmwareData.kext
BrcmPatchRAM2.kext
4. DSDT屏蔽独显（参照9550例子）
![屏幕快照 2017-04-29 上午12.03.08](https://lh3.googleusercontent.com/-bM2_y5XVEgs/WQNnyEwpFKI/AAAAAAAAAu8/P3VyWnArqHc4rXAvpYoGsjmEDgD8Cqz7gCHM/I/%255BUNSET%255D)

5. AppleLPC启用（参照9550例子）
6. 声卡驱动
VoodooHDA.kext
7. 电源管理ACPIBatteryManager.kext
8. 键盘+触摸板驱动
ApplePS2SmartTouchPad.kext
9. UHD屏幕驱动
CoreDisplayFixup.kext
Lilu.kext
10. CPU睿频和多档位
1 10.12更换为MacBookPro13,1
2 安装HWPEnabler.kext
3 勾选HWPEnable
![屏幕快照 2017-05-16 下午14.12.15 下午](https://lh3.googleusercontent.com/-vlJLQR_zyQw/WRqZD_U09BI/AAAAAAAAAvg/4p8LEFbOtfU3zGLrwSjekE7jRmSI6XaowCHM/I/%255BUNSET%255D)
![屏幕快照 2017-05-16 下午14.14.51 下午](https://lh3.googleusercontent.com/--QCef5txW_o/WRqZIuyfXzI/AAAAAAAAAvk/ZrdzPzpSlzMRuptoOjrSSU-7LcbjXzzAgCHM/I/%255BUNSET%255D)


11. drivers64UEFI
很重要，不然可能出现时不时进不了系统的故障。
12. 亮度调节
DSDT打补丁测试不行。所以暂时使用ScreenShade
13. 双系统下触控板设置问题
使用Karabiner暂时解决（CMD和CON的切换）
14.双系统时间相差问题。使用LoaclTimeToggle.pkg解决

15. 双系统蓝牙配对问题
   http://www.insanelymac.com/forum/topic/268837-dual-boot-bluetooth-pairing-solved/
    修改LinkID使Mac下蓝牙鼠标正常配对。
    
16. intel 睿频最优Smbios
设置成17.1，勾选Mobile选项  

17. 亮度调节
    添加AppleBacklightInjector.kext，删除intelBacklight.kext。
    在config.plist中添加
    
```
<dict>
	<key>Comment</key>
	<string>change F%uT%04x to F%uTxxxx for AppleBacklightInjector.kext (credit RehabMan)</string>
	<key>Disabled</key>
	<false/>
	<key>Find</key>
	<data>RiV1VCUwNHgA</data>
	<key>Name</key>
	<string>com.apple.driver.AppleBacklight</string>
	<key>Replace</key>
	<data>RiV1VHh4eHgA</data>
</dict>
```    
18. 增加睿频自动关闭
![屏幕快照 2017-05-05 15.26.14](https://lh3.googleusercontent.com/-B0BzXCF4o4k/WQwpL_GNplI/AAAAAAAAAvQ/--K96HItaLEtSica9J-0bC39MhZA_2OtQCHM/I/%255BUNSET%255D)



