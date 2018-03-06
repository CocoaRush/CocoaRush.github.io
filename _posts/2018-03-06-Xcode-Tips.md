---
layout:     post
title:      Xcode Tips
subtitle:   IDE 实用小技巧
date:       2018-03-06
author:     Pitt
header-img: img/post-bg-25.jpg
catalog: true
tags:
    - 2018.03
    - Tips
---

## 清理 Xcode 占用的磁盘空间
吓我一跳，Xcodo居然占用了 100G 的磁盘空间～

#### Derived Data

可重新生成；会删除build生成的项目索引、build输出以及日志。重新打开项目时会重新生成，大的项目会耗费一些时间。

Go to `~/Library/Developer/Xcode/DerivedData/`


#### iOS Device Support

移除对旧设备的支持，连接设备调试时，会重新自动生成

Go to `~/Library/Developer/Xcode/iOS DeviceSupport/`


#### Archives (Organizer)

不可恢复；Adhoc或者App Store版本会被删除。建议备份dSYM文件夹

Go to `~/Library/Developer/Xcode/Archives/`


#### Simulators

移除旧版本的模拟器支持，可重新下载了

Go to `~/Library/Developer/CoreSimulator/Devices`   
Go to `~/Library/Application Support/iPhone Simulator/`


#### Documentation

不可恢复；将删除旧的 DocSets文档

Go to `~/Library/Developer/Shared/Documentation/DocSets`


**End**
