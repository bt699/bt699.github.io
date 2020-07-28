---
layout: post
title:  "vmware-ubuntu194"
date:   2020-07-28 13:19:48 +0800
categories: python

---
# vmware-ubuntu194 #
用vmware安装ubuntu19.4重置密码。
按F2 进入菜单 
选择高级Advanced option for Ubuntu  点击回车
选择带有（recovery mode）,
不要点击回车，如何点击回车Give root password for maintenance这个错误
必须按下E键，进入下一个界面。
找到的“recovery nomodeset”改为“quiet splash rw init=/bin/bash”
接着按F10或者Ctrl+x 后 在命令行内输入passwd后进行修改密码即可
关机，或者强制关机后，就能用新设置的密码登录了。
