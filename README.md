# MSI - GS63 - 7代 笔记本 EFI项目
hackintosh: gs63-7re the efi files of devices....

黑苹果 MSI G*62/63 - 7* 笔记本的 EFI维护项目(*代表任意字符)
	因MSI的该系列主板采用相同的配置的内建硬件,故可以通用.*详细的的通用将在支持机型里面说明

支持的操作系统级别:
macOS 10.13.6 (推荐使用)
	使用该系统支持 本机自带的独立显卡,支持GPU显卡加速
macOS 10.14
	支持独立显卡,但是不支持GPU显卡加速
macOS 10.15
	不支持独立显卡,使用核心显卡

存在的一些问题在下文中指出,适配度在百分之85以上了
	调节屏幕亮度; 百分之5
	读卡器+摄像头:百分之5
	HDMI + DP : 百分之5

# 目录
1,支持机型
2,项目进度
3,硬件检测
4,完整度数
5,解决方案
6.尚未解决
7,待解/无解 --- 问题
8,项目资源

#项目说明
	
	Devices: 存放支持机型的 clover efi 文件
	Resources: 存放资源文件
	Extra: 所有GS6系列7代处理器的 驱动文件,适配出自己的机型的驱动要自己从这个里面拿文件测试
	Tools: 工具文件存放目录
	README : 说明文件
	README_en : 英文版说明文件 

*Apache License, 2.0 (Apache-2.0)
*BSD 3-Clause "New" or "Revised" license (BSD-3-Clause)
*BSD 3-Clause "Simplified" or "FreeBSD" license (BSD-2-Clause)
*GNU General Public License (GPL)
*GNU Library or "Lesser" General Public License (LGPL)
*MIT license (MIT)
*Mozilla Public License 1.1 (MPL-1.1)
*Common Development and Distribution License (CDDL-1.0)
*Eclipse Public License (EPL-1.0)


#1,支持机型
	本项目主要维护机型: GS63-7RE,以下测试说明均来自该机型

	机型 - 对应 EFI clover 文件
		GS63-7RE (主要维护机型)

	GL62系列
		GL62M-7RE

		*由于GS6系列第7代主板采用相同配置,均可以使用.特别维护机型区别在于,体验感更好.
		通用机型适配度:百分之75以上; 指定维护机型适配度:百分之85以上

	其他机型的维护推荐目录
	https://blog.daliansky.net/Hackintosh-long-term-maintenance-model-checklist.html


#2,项目进度
macOS10.13.6 :百分之85,独显+GPU视频加速;
10.14: 独显,无视频加速
10.15: 无独显
*详细看硬件检查报告信息,方便进一步开发维护该机型的 hackintosh 项目



#3,硬件检测
型号名称: MACBook PRO
型号标识符:MACBook14.3
处理器名称:Inter Core i7[i7-7700HQ]
SMBIOS: MacBookPro14,3 原生支持芯片I7 7700HQ

ATA: 无
FireWire: 无
Nvme: 支持
PCI: 无
SAS: 无
SATA: 支持
SPI: 无
USB: 3*usb3.0  1*usb2.0  支持USB无线网卡,无线鼠标,集线器等USB设备
以太网卡: killer E2500 支持
无线网卡: killer N1535 不支持(暂时没有方案解决该网卡)
存储: 支持
光盘刻录: 无
光纤通道: 无
内存: 2133 – 2600  DDR4   8<X<32G
图形显卡: HD inter HD graphics 630,内建自带核显 1536MB
		  系统10.13.6 支持webdriver NVIDIA显卡GTX1050ti
并行SCSI: 无
打印机: 支持,2.2.5(cups-462.2.9)
控制器: 无
摄像头: 无驱动
电源: 支持,读取(型号,电量信息,效能分析,电流/电压,交流电源),睡眠,合盖睡眠唤醒
硬件RAID: 无
蓝牙: 不支持
开机自检: 通过(加载系统进度条到一半有短暂闪屏不影响使用)
读卡器: 不支持
雷劈: 没有硬件
音频: 完全支持使用[speaker(Anolog)*2, SPDIF-OUT, microphone(digital) ,microphone(Black rear) ,digital-out(HDMI)]


#4,完整度数
接近百分之90的原生适配度,出现的问题在下列中说明*

#5,解决方案
该解决方案指出的是 无线网络方案
方案一: 外置 USB无线网卡,推荐 USB3.0 876+300M 无线网卡
方案二: 内置 购置苹果拆机无线网卡+NGFF转接卡,该机型已经解决USB口问题,完美支持USB通道蓝牙
    BCM94331CD (4 antenna, BT4, Wifi a/b/g/n): iMac Intel 21.5” or 27” (Late 2012-Early 2013)

    BCM94360CD (4 antenna, BT4, Wifi a/b/g/n/ac): iMac Intel 21.5” or 27” (Late 2013-Late 2014)

    BCM943602CD (4 antenna): Couldn’t find corresponding model

    BCM943602CDP (4 antenna, BT4 Wifi a/b/g/n/ac): iMac Intel 21.5” or 27” (Mid 2015-Late 2015)

    BCM94360CS (3 antenna, BT4, Wifi a/b/g/n/ac): Mac mini A1347 (Late 2014), MacBook Pro 13” and 15” Retina (Late 2013-Mid 2014)

    BCM943602CS (3 antenna, BT4, Wifi a/b/g/n/ac): MacBook Pro Retina (2015)

    BCM94360CS2 (2 antenna, BT4, Wifi a/b/g/n/ac): MacBook Air (Mid 2013-2017)

    BCM94360CSAX (3 antenna, BT4, a/b/g/n): MacBook Pro 13” and 15” Retina (Late 2012-Early 2013)

#6,尚未解决 
可以解决的方案,但尚未处理,期待各位携手一起处理
1,屏幕亮度调节 	(体验问题)
2,读卡器功能		(功能问题)
3,摄像头无法使用	(功能问题)
4,HDMI无法使用 : 不知道是不是设置问题,GTX1050TI显卡可以运行,HDMI音频又可以播放


其他问题的发掘期待使用中提交

#7,待解/无解 --- 问题
1,内置无线网卡 killer N1535 无法驱动

#8,项目资源
1,clover configuration 工具
2.webdriver NVIDIA显卡驱动
3,音频补丁(无音频笔记本可使用)