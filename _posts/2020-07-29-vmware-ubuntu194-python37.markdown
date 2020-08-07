---
layout: post
title:  "vmware-ubuntu194"
date:   2020-07-28 13:19:48 +0800
categories: python

---
# vmware-ubuntu194 #
用vmware安装ubuntu19.4
选必须选择【update to the new installer】
即安装不选ssh。
硬盘选Guided - use entire disk and set up LVM
等更新完成自动刷新，
即可成功安装

查看ubuntu的ip 答：ifconfig

替换源
sudo vi /etc/apt/sources.list

复制阿里源 [](https://developer.aliyun.com/mirror/ubuntu?spm=a2c6h.13651102.0.0.3e221b11BskBlO)

更新源 sudo apt-get update

安装SSH服务器
sudo apt install openssh-server

安装python3.7

默认apt install python3安装时3.8

apt install python3.7安装3.7版

访问python3.7改默认
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 150
即可python3访问

安装pip
sudo apt install python3-pip

卸载 apt autoremove python3-pip

python3 -m pip install paddlepaddle -i https://mirror.baidu.com/pypi/simple
提示没有找到，更新pip

ERROR: Could not find a version that satisfies the requirement paddlepaddle (from versions: none)
ERROR: No matching distribution found for paddlepaddle
 更新pip
 python3 -m pip install --upgrade pip
 
 paddlepaddle 不支持 python3.8
 
 安装python3.7 