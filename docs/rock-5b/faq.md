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

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

### root密码是多少

官方系统为root的初始密码为rock，armbian的初始root密码为1234

### 支持qc

不支持，仅支持pd

### 串口怎么接

看[wiki页面](https://wiki.radxa.com/Rock5/guide/serial-console)

### GPU驱动能不能用

linux下只有opengl-es，等于不能用  
Android下可以用  

### 体质怎么测试

执行以下指令，看 pvtm=？   
值越高体制越好  
```bash
dmesg | grep pvtm
```

### pd重启怎么办

暂时无解，官方正在改软件，一个将就的办法就是不用pd直接固定电压供电  

### 能不能用扩展坞

可以用，但是不保证兼容性

### 能不能用sata

背面的m2接口不支持sata固态

### 要不要买emmc

看个人需求，如果受不了tf卡的速度可以考虑  
linux可以直接使用nvme启动

