---
layout: post
title: Android APP - 自动执行外置SDcard中特定名称的脚本文件
category: ANDROID
tags: [ ]
---

## 自动执行外置SDcard中特定名称的脚本文件

------
AutorunSDScript.apk 使用说明
功能：自动执行外置SDcard中特定名称的脚本文件。
适用：需要执行一批adb命令的场景，把命令写入脚本，方便非软件人员小范围测试。

1. 首先需要破解机器的root权限（必须通过其它工具）；
2. 在外置SDcard根目录中放入脚本文件 autorun_plug.sh 和 autorun_unplug.sh;
3. 当插入SDcard时，autorun_plug.sh 自动执行；
4. 当拔出SDcard时，autorun_unplug.sh 自动执行；
5. 根据需要你可以只使用一个脚本；
5. app注册了一个service监控SDcard插拔的动作，所以app不需要保持在前台。"


## 思路

------
1. 首先注册一个service，参考[Android Service Example](http://examples.javacodegeeks.com/android/core/service/android-service-example/)

2. 然后在service中注册一个broadcast listener，用于监听external sdcard插拔事件，参考[android how to listen for the upper application sdcard plug event](http://www.phonesdevelopers.com/1792206/)

3. 最后在java中执行unix命令，参考[How to execute system commands (linux/bsd) using Java](http://stackoverflow.com/questions/792024/how-to-execute-system-commands-linux-bsd-using-java)


## 源码

------
[已上传GitHub](https://github.com/li2/autorun-shell-script-when-sdcard-pluged)


GitHub使用入门指南

- [GitHub Help: Set Up Git](https://help.github.com/articles/set-up-git)
- [GitHub Help: Create A Repo](https://help.github.com/articles/create-a-repo)
- [助你入门 git 的简明指南](http://rogerdudler.github.io/git-guide/index.zh.html)

------
by li2-    2014-04-11 沪北
