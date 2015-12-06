---
layout: post
title: Career 3th
permalink: /3th/
---

这个页面记录了我在二零一零年从一个二本电子信息工程专业毕业后来上海，迄今五年的工作历程，以时间为轴。

*PS: 好多简历模板是先写最近的职业经历，降序排列。但我觉得自己的每个阶段都是有衔接的，所以就按升序排列了。如果您对之前的不感兴趣，[请直接跳到最后，传送门](http://li2.me/career-3th/#top2)*  : )

[我的GitHub](https://github.com/li2)
[我的SegmentFault](http://segmentfault.com/u/li2)
[我的StackOverFlow](http://stackoverflow.com/users/2722270/li2)


## 2010.12~2012.11 单片机软件

用C语言编写程序，运行在32位ARM Cortex M3单片机上。编写过的代码，概括起来包括：

- 键盘扫描、继电器控制、LED等GPIO模块；
- 液晶菜单；
- 485总线/CAN总线通信模块；
- 中断处理模块；
- 如果项目稍复杂，裸机程序就需要跑到ucOS上。

代码需要在硬件上调试，不时需要飞线、更改电阻电容、替换烧坏的零部件比如MCU，所以我是**一个拿得起电烙铁的软件工程师**。
这个阶段只整理出了一篇值得公开分享的技术笔记：[基于二叉树的多层的液晶菜单界面设计](http://li2.me/hardware/基于二叉树的多层的液晶菜单界面设计/)


## 2013.01~2014.06 Android驱动

维护Android驱动（C语言），移植到新的硬件平台。
坦白讲，这个阶段写的代码最少。不需要开发全新的驱动程序，只需要维护现有的成熟驱动，或者公板供应商提供的BSP内的驱动。所谓维护，也仅仅是根据新的硬件电路图及硬件手册，修改必要的引脚或者寄存器配置，然后调用Linux API注册驱动，或者配置相应的总线。

但为了完成上面提到的事情，是需要付出较多努力的：

- Linux驱动模块（字符设备驱动、TTY设备驱动、I2C设备驱动）；
- 搭建Ubuntu开发编译环境；
- 编译Android BSP，或者编译其中某个驱动模块，或者编译某个Android App；
- 使用ADB直接操作Android机器（修改配置文件、卸载/加载驱动、修改文件权限）；
- 从win机器上远程访问Ubuntu机器；
- 使用命令行、Shell；
- SVN；

这个阶段整理出十几篇笔记：[『Linux设备驱动程序笔记』](http://li2.me/ldd/Linux-Device-Drivers/) [『Ubuntu分类』](http://li2.me/categories/#util) [『Shell分类』](http://li2.me/categories/#shell)


## 2013.08~迄今 Android App

### 2013.08 我的第一个App: I2C Tool

App用于探测Android设备I2C总线、读取/设置I2C设备寄存器值，并写入Log，方便不熟悉命令行和ADB的硬件工程师抓取寄存器值。
之所以开发这个App，是因为我负责的驱动模块出现了问题，需要和硬件工程师一起排查软、硬问题。而硬件工程师不熟悉命令行、ADB，并且使用ADB打印的Log不便于处理。

在2013年8月完成第1版，这是第1次开发Android App（不懂Android，不懂Java，全靠搜索，代码非常糟糕），然后在2015年10月重构了代码，[你可以从这里获取源码](https://github.com/li2/Android_I2C_Tool)，核心是通过 `Runtime.getRuntime().exec()` 执行命令行工具，然后读取进程的标准输出/标准错误，再做进一步的解析处理。

![i2cset](/images/career/set.png)

在驱动开发的这段时间里，还写过一个简单的App，用来监听SD卡插拔事件，然后执行SD卡中的脚本文件。也是为了方便测试驱动。[你可以从这里获取源码](https://github.com/li2/Autorun_Script_When_Sdcard_Pluged)。

期间还维（学）护（习）了一个App，这个App直接打包在我厂Android机器内，通过Service定期检查GPS星历资料，如有更新即下载。整理了一份笔记，[你可以点开这里看](http://li2.me/android/Download-Files-by-FTP/)。


**2014年10月份，部门组织架构调整，大概是由于上述几个App，我从驱动岗位调到App岗位。**


### 2014.10~2015.11 我的第一个上架App: Magellan Active

一款运动App，但它本身不产生数据，数据来源于我厂的一款运动手表，主要功能是向手表的用户展示数据。
App的功能模块包括：从手表抓取数据、上传数据到云端、SQLite数据库、OAuth2.0、UI。
我负责完成其中大部分的UI模块，下图是UI的版本变化：

![magellan-active-versions](/images/career/magellan-active-versions.png)

下面是GIF演示：

![android-gif-demo](/images/career/magellan-active-android-gif-demo.gif)

图示的界面主要使用了`GridView`, `ViewPager`, `Fragment`，使用了开源库`holographlibrary`和`viewpagerindicator`。用户点击day/30day按钮时切换到对应图表。

开发过程中填过最大的坑之一是`ViewPager`和`Fragment`，因为不懂其中的机制，导致ViewPager中的Fragment没有被更新，或者崩溃。此后花了很大精力在这一块，写了一个demo演示如何更新及替换ViewPager的Fragment，[你可以从这里查阅源码，ReadMe展示了我对此的思考和总结](https://github.com/li2/Update_Replace_Fragment_In_ViewPager)。

App从2014年10月开始开发，小组4个人；2015年4月份左右在Google Play上架。
同时期，iOS版本也在开发中，稍后讲到。


### 2015.05~2015.08 英文有声读物App

这个App实现了《麦田守望者》全部语音和文本的同步：**被读到的单词可以高亮显示，点击单词可以跳到对应的音频位置播放**。之所以开发这个App，是因为想练习听力，顺带练习编程。我在SegmentFault的专栏里，对开发过程做了详细的记录和分析，[你可以点击这里阅读](http://segmentfault.com/a/1190000003498111)，然后[从这里获取源码](https://github.com/li2/TalkingBook21_AndroidApp)。
下面是GIF演示：

![demo](/images/career/TalkingBook21_demo.gif)


开发这个App的过程中，在一个开源代码的基础上**实现了一个类似网易云音乐歌词功能的 LrcView**，完成「上下滚动歌词」功能： 「上下滚动歌词」满足用户查看「非当前正在播放处歌词」的需求，超时后「上下滚动歌词」后回滚到「当前正在播放处」。本来想用它展示英文文本，后来弃用。[你可以从这里查阅源码](https://github.com/li2/Android_Lrc_View)。

![lrcview](/images/career/lrcview.png)



## 2014.10~迄今 iOS App

### 2014.10~2015.11 Magellan Active iOS版

在开发Magellan Active Android版本时，小组同步开发iOS版本，按照相同的UI Spec。使用`UICollectionView`完成了主界面的搭建，所有的graph通过纯代码自定义cell实现。
下面是GIF演示：

![ios-sleep](/images/career/magellan-active-ios-gif-demo.gif)

我目前对iOS的了解还非（基）常（本）粗（靠）浅（搜）。

------

结束。呃 我是不是写的太啰嗦了（好吧 也许你只浏览了一小部分 就关闭页面了呢（。
