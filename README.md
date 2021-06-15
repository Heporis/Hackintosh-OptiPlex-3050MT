# Hackintosh-OptiPlex-3050MT

## 简介

这是Dell OptiPlex 3050MT的黑苹果EFI文件夹，对于3050的三种型号基本通用。包含opencore 0.7.0配置和clover 5109配置，前者支持最新macOS big sur 11.4，后者只测试了macOS Catalina 10.15.6。使用之前，你需要补充SMBios信息。

## 硬件配置

* **主机**：Dell OptiPlex 3050MT
* **CPU**:  Intel® Core™ i5-7500
* **GPU**: Intel® HD Graphics 630
* **RAM**: 16GB DDR4 2666 Daul Channel
* **SSD**: Samsung 860 EVO 250G 
* **Ethernet**: Realtek RTL8168/8111
* **Audio**:Realtek ALC255(3234)

## 不正常工作

* 睡眠唤醒后黑屏（HDMI）

## BIOS 设定

* 恢复factory defaults
* General → Advanced Boot Options：***取消勾选***
* System Configuration → SATA Operation: ***AHCI***
* System Configuration → Serial Port: ***Disabled***
* Secure Boot → Secure Boot Enable: ***Disabled***
* Virtualization Support → VT for Direct I/O: ***取消勾选***
* 将EFI-shell文件夹复制到U盘，改名为EFI，然后从U盘启动
* 设置 Pre-Allocated DVMT 为 64M: 
  ***setup_var 0x795 0x02***
* 禁用 CFG lock: 
  ***setup_var 0x4ed 0x00***

## 麦克风修复

- 需要CodecCommander.kext

- 运行ComboJack_Installer/install.sh，然后重启

- 插入耳机时，会弹出对话框询问你插入的是耳机还是耳塞
