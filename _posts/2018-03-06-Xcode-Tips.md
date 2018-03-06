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
    - Fixed
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



## Xcode-beta

今天手贱用 Xcode-beta 打开了之前 Xcode8 的一个项目，而且升级了 Xcode-beta 推荐的各种自动优化，差一点还自动转化成 Swift4 了。接下来各种问题就来了，好多第三方的 Framework 都还不支持。所以立马想着用原来的 Xcode8 继续，但一编译就各种报错。


#### 第三方 Framework 不支持

解决方案：（在 Preferences -> Locations 里面)

切换  Command Line Tools 到 Xcode 9.0，神奇。


#### Simulator 消失

另一个问题，安装 Xcode-beta 后，Xcode 8 里面的 Simulator 立马就不见了。

解决方案：

Open Developer Tools -> Simulator 之后重启 Xcode 就找回来了。注意：两个 Xcode 不可以同时使用 Simulator。



## Xcode Warning

#### no rule to process ...

`warning: no rule to process file 'xxx' of type xxx for architecture xxx`

解决方案：

文件 xxx 出现在了Xcode中的：TARGES → Build Phases → Compile Sources中，移除即可解决问题。



**End**
