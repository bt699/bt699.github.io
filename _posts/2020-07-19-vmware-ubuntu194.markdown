---
layout: post
title:  "vmware-ubuntu194"
date:   2020-07-15 13:19:48 +0800
categories: python

---
# vmware-ubuntu194 #
用vmware安装ubuntu19.4时一直提示安装失败。
排查原因：必须选择【update to the new installer】即成功安装。不要选择【continue without updating】否作安装失败。

查看ubuntu的ip 答：ifconfig

替换源
sudo vi /etc/apt/sources.list

cn.archive.ubuntu.com/ubuntu替换为mirrors.aliyun.com
:%s#cn.archive.ubuntu.com/ubuntu#mirrors.aliyun.com/#g

:%s#aliyun.com#aliyun.com/ubuntu#g

:%s#aliyun.com/ubuntu#aliyun.com/ubuntu/#g

复制20.4源文件
[](https://developer.aliyun.com/mirror/ubuntu?spm=a2c6h.13651102.0.0.3e221b11BskBlO)

保存退出
:wq

安装python27
$ sudo apt-get update

$ sudo apt-get install python2.7

$wget https://bootstrap.pypa.io/get-pip.py

$python2.7 get-pip.py

$python2.7 -m pip install paddlepaddle -i https://mirror.baidu.com/pypi/simple

ImportError: libgomp.so.1: cannot open shared object file: No such file or directory

$sudo apt-get install libgomp1

ImportError: libgomp.so.1: cannot open shared object file: No such file or directory

$sudo apt-get install libsm6 libxrender1 libfontconfig1

$python2.7

>>> import paddle.fluid
>>> paddle.fluid.install_check.run_check()
Running Verify Fluid Program ...
Your Paddle Fluid works well on SINGLE GPU or CPU.
W0719 05:59:28.002332 15488 build_strategy.cc:170] fusion_group is not enabled for Windows/MacOS now, and only effective when running with CUDA GPU.
W0719 05:59:28.003418 15488 fuse_all_reduce_op_pass.cc:74] Find all_reduce operators: 2. To make the speed faster, some all_reduce ops are fused during training, after fusion, the number of all_reduce ops is 1.
Your Paddle Fluid works well on MUTIPLE GPU or CPU.
Your Paddle Fluid is installed successfully! Let's start deep Learning with Paddle Fluid now

安装成功。







