---
layout:     post
title:      iOS Coding Tips
subtitle:   开发过程中遇到的一些小技巧，事半功倍！
date:       2017-12-08
author:     Pitt
header-img: img/post-bg-7.jpg
catalog: true
tags:
    - 2017.12
    - iOS
---


## iOS UI

#### iOS Status Bar Appearance

全局设置所有 View Controller 的 Status Bar 状态，不用每个 Controller 重载顶部状态栏风格，主要对需要设置为白色的项目有用，系统默认为黑色。

In order to change the color of status bar once for all we have do two changes:

* First define the property of `View Controller-based status bar` property in your info.plist file (set it to **NO**)

* Then define the color of status bar in `didFinishLaunchingWithOptions` function in AppDelegate.swift (This will affect to all view controllers in your app)

```
application.statusBarStyle = .lightContent
application.isStatusBarHidden = false
```


**End**
