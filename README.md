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
10. CPU睿频
参照9550变频
![屏幕快照 2017-04-27 上午11.33.07](https://lh3.googleusercontent.com/-6QT_pUZkw3I/WQNlQUu2xEI/AAAAAAAAAus/zkAz7bPP364YKNyQNJWM7m2MyC5JnXy-QCHM/I/%255BUNSET%255D)

![屏幕快照 2017-04-28 下午11.53.23](https://lh3.googleusercontent.com/-mDMsRST9cvI/WQNlgPWqpwI/AAAAAAAAAuw/SLy8J7j3cDMFWFrqjptRSJXS5_1kvwq7ACHM/I/%255BUNSET%255D)
11. drivers64UEFI
很重要，不然可能出现时不时进不了系统的故障。
12. 亮度调节
DSDT打补丁测试不行。所以暂时使用ScreenShade
13. 双系统下触控板设置问题
使用Karabiner暂时解决（CMD和CON的切换）
14.双系统时间相差问题。使用LoaclTimeToggle.pkg解决

 



