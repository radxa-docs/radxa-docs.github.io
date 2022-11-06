---
id: rock-5b-faq
title: rock 5b faq
description: rock 5b faq
tags:

- rock-5b
- faq

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [root密码是多少](#root%E5%AF%86%E7%A0%81%E6%98%AF%E5%A4%9A%E5%B0%91)
- [支持qc](#%E6%94%AF%E6%8C%81qc)
- [串口怎么接](#%E4%B8%B2%E5%8F%A3%E6%80%8E%E4%B9%88%E6%8E%A5)
- [GPU驱动能不能用](#gpu%E9%A9%B1%E5%8A%A8%E8%83%BD%E4%B8%8D%E8%83%BD%E7%94%A8)
- [体质怎么测试](#%E4%BD%93%E8%B4%A8%E6%80%8E%E4%B9%88%E6%B5%8B%E8%AF%95)
- [pd重启怎么办](#pd%E9%87%8D%E5%90%AF%E6%80%8E%E4%B9%88%E5%8A%9E)
- [能不能用扩展坞](#%E8%83%BD%E4%B8%8D%E8%83%BD%E7%94%A8%E6%89%A9%E5%B1%95%E5%9D%9E)
- [能不能用sata](#%E8%83%BD%E4%B8%8D%E8%83%BD%E7%94%A8sata)
- [要不要买emmc](#%E8%A6%81%E4%B8%8D%E8%A6%81%E4%B9%B0emmc)
- [在linux下运行geekbench5跑分](#%E5%9C%A8linux%E4%B8%8B%E8%BF%90%E8%A1%8Cgeekbench5%E8%B7%91%E5%88%86)
- [SOC是否需要外加散热措施](#soc%E6%98%AF%E5%90%A6%E9%9C%80%E8%A6%81%E5%A4%96%E5%8A%A0%E6%95%A3%E7%83%AD%E6%8E%AA%E6%96%BD)
- [linux下查看温度和pd协商功率](#linux%E4%B8%8B%E6%9F%A5%E7%9C%8B%E6%B8%A9%E5%BA%A6%E5%92%8Cpd%E5%8D%8F%E5%95%86%E5%8A%9F%E7%8E%87)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

### root密码是多少

官方系统初始用户名密码为下表中的一个

| 用户名  | 密码   |
|------|------|
| rock | rock |
| root | rock |

armbian远程ssh连接的初始root密码为1234，首次本地登录默认不需要密码直接进入armbian初始化程序

### 支持qc

不支持，仅支持pd

### 串口怎么接

看[wiki页面](https://wiki.radxa.com/Rock5/guide/serial-console)

### GPU驱动能不能用

linux下只有opengl-es，等于不能用  
Android下可以用

### 体质怎么测试

linux命令行执行以下指令   
值越高体质越好

```bash
dmesg | grep -E 'pvtm|dmc' | grep sel
```

数值说明：

|                 参数                 |   说明    |
|:----------------------------------:|:-------:|
|      cpu cpu0: pvtm-volt-sel       |  小核簇体质  |
|      cpu cpu4: pvtm-volt-sel       | 大核心簇1体质 |
|      cpu cpu6: pvtm-volt-sel       | 大核心簇2体质 |
|  mali fb000000.gpu: pvtm-volt-sel  |  GPU体质  |
| rockchip-dmc dmc: leakage-volt-sel | 内存控制器体质 |
| RKNPU fdab0000.npu: pvtm-volt-sel  |  NUP体质  |

### pd重启怎么办

暂时无解，官方正在改软件，一个将就的办法就是不用pd直接固定电压供电

### 能不能用扩展坞

可以用，但是不保证兼容性

### 能不能用sata

背面的m2接口不支持sata固态

### 要不要买emmc

看个人需求，如果受不了tf卡的速度可以考虑  
linux可以直接使用nvme启动  
Android目前发布了第一版可以nvme启动的固件

### 在linux下运行geekbench5跑分

注意：目前geekbench5 for arm64处于preview状态  
在linux的root命令行中运行以下指令

```bash
mkdir -p ~/software/geekbench5 && cd ~/software/geekbench5 
wget https://cdn.geekbench.com/Geekbench-5.4.0-LinuxARMPreview.tar.gz
tar xf Geekbench-5.4.0-LinuxARMPreview.tar.gz
cd Geekbench-5.4.0-LinuxARMPreview
./geekbench_aarch64
```

执行完成后会有以下输出：

```text
Uploading results to the Geekbench Browser. This could take a minute or two
depending on the speed of your internet connection.

Upload succeeded. Visit the following link and view your results online:

  https://browser.geekbench.com/v5/cpu/18158036

Visit the following link and add this result to your profile:

  https://browser.geekbench.com/v5/cpu/18158036/claim?key=545201
```

其中 *https://browser.geekbench.com/v5/cpu/18158036* 这样的链接就是跑分结果页面

### SOC是否需要外加散热措施

需要外加散热措施，否则将在较长时间（依赖于气温，气温20度左右大概2-3分钟）的高负载的时候会触发温度墙导致降频

### linux下查看温度和pd协商功率

执行以下指令安装所需软件包（需要网络）

```bash
sudo apt update 
sudo apt install lm-sensors
```

软件包安装完成后执行以下指令查看

```bash
sensors
```




