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


#### Disable CALayer animation delays

当我们想动态的改变 `CALayer` 的一些 Animatble 的参数时，常常会看到一些延时，特别是随着手指的移动来改变 `frame` 的大小时，延时非常明显，这是因为系统把每一次参数改变都当作一次动画来处理，而一次动画的默认时间为 0.25 秒。采用下面的方式可以取消这个动画时间。

``` swift
CATransaction.begin()
CATransaction.setDisableActions(true)
layer.frame = colorBar.bounds
CATransaction.commit()
```

**End**
