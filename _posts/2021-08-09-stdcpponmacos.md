---
title: Mac 上 bits/stdc++.h 头文件无法使用简单解法
date: 2021-08-09 09:29:40
categories:
- 开发
- 工具
tags: 开发 C++ Xcode MacOS
---

前段时间，我在 Mac 上使用 CLion 进行 C++ 编译，但发现 `#include<bits/stdc++.h>` **居然出了问题，无法使用**，Xcode 也不行。
我试图查找资料，但一般都要求重装编译器😂。

**想着省事，我测验并应用了这种方法，可以简单配置使用"bits/stdc++.h"头文件。**

<!-- more -->

## 解决方案

首先，下载[这个文件](https://antdock-my.sharepoint.com/:f:/g/personal/ericzhang_antdock_onmicrosoft_com/EtC9nen85bNEjWD6ZxwpzKIBXNgPeXeQg5fkABB7tCObyg?e=ANgwOa)（stdc++.h），当中已经写好了内容。如果打开你会发现，里面其实是一长串的头文件，起到偷懒（误）简化的作用。

接下来，打开"访达"，点击菜单栏中的前往----前往文件夹，

![打开前往文件夹的屏幕截图](https://z3.ax1x.com/2021/08/10/fG0cHU.png)

输入以下路径：

```
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include
```

进入一个满载各类文件的文件夹。

你会发现，很多常用的头文件都在这里。

现在，新建一个文件夹，命名为 bits 。

![新建bits文件夹的屏幕截图](https://z3.ax1x.com/2021/08/10/fG06BT.png)

然后将刚才下载的 stdc++.h 这个头文件放入 bits 文件夹。

![放入文件的屏幕截图](https://z3.ax1x.com/2021/08/10/fG0yuV.png)

现在就可以正常使用"bits/stdc++.h"头文件了。

## 一点感想

其实，原来我有点记不住各个头文件的名称，尤其是这个"bits/stdc++.h"，我老是写错。

这次我才知道，bits是个文件夹，/是路径的意思，stdc++是一个头文件，而.h是扩展名，这样就记住了！