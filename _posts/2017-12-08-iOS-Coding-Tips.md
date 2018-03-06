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
    - Tips
    - Fixed
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



## WKWebView

#### 本地资源
WKWebView 加载本地资源需要给一个授权访问的文件夹：   
`[_webView loadFileURL:url allowingReadAccessToURL:dir];`   
如果超出这个文件范围外，就不能访问了，这会导致有些本地资源读取到不到，比如创建一个图片缩略图，放到临时文件夹里面了，这时再用WKWebView显示这张缩略图时，就显示不出来了。

注意：本地图片的路径得加上前缀 `file://`，完整的路径为：
`file:///var/mobile/Containers/Data/Application/8089B76A-8246-43FD-8A26-F24BB97B847A/Documents/ThumbImages/IMG_0027.jpg`


**End**
