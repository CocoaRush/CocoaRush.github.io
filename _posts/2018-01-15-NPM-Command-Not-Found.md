---
layout:     post
title:      Command Not Found with a Node Module 
subtitle:   The NPM installed module not found solution
date:       2018-01-05
author:     Pitt
header-img: img/post-bg-20.jpg
catalog: true
tags:
    - 2018.01
    - JavaScript
    - Fixed
---


## Problem
I ran the following command for installing XXX (a node package module) globally: 
```
npm install -g XXX
```

The installation succeed but when I ran this XXX command in the command line I got a `XXX: command not found` error. It appeared that it installed **XXX*** in my local folder that is `/Users/YOURUSERNAME/node_modules` and not in the **global** NPM folder.

You can check this by running this command: `npm root or npm root -g`, which was returning my personal directory `/Users/YOURUSERNAME/node_modules` and not the expected `/usr/local/lib/node_modules`.

After some trial & error, I finally found the solution. You have to change the **npm config prefix** like so: `npm config set prefix /usr/local`

Then when I re-ran `npm root -g`, I got the correct root folder: `/usr/local/lib/node_modules`

When I reinstalled XXX globally (with the `-g param`) it finally worked and appeared that it was now correctly installed in the global NPM folder. Yeay!


## NPM Packages
There are two ways to install npm packages: `locally` or `globally`. You choose which kind of installation to use based on how you want to use the package.

If you want to use it a package as a command line tool, something like the **grunt CLI**, then you want to install it `globally`. This way, it works no matter which directory is your current directory.

If you want to depend on the package from your own module using something like Node's require, then you want to install `locally`.


**End**
