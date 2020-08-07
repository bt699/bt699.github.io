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

putty.exe登录失败
#sudo vi /etc/ssh/sshd_config 
去掉前面的# 打开 PermitRootLogin yes
重启ssh sudo servie ssh restart 
重启ssh sudo servie sshd restart

查看ubuntu的ip 答：ifconfig

替换源
sudo vi /etc/apt/sources.list

复制阿里源 [](https://developer.aliyun.com/mirror/ubuntu?spm=a2c6h.13651102.0.0.3e221b11BskBlO)

更新源 sudo apt-get update

python3 -m pip install paddlepaddle -i https://mirror.baidu.com/pypi/simple
提示没有找到，更新pip



 更新pip
 python3 -m pip install --upgrade pip
 
 paddlepaddle 不支持 python3.8
 
 安装python3.7 