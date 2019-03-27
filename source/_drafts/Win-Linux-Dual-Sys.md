---
layout: draft
title: Win_Linux_Dual_Sys
date: 2019-03-24 18:22:56
updated: 
thumbnail: 
categories: 
tags: [Windows,Linux]
comments: true
permalink: true
toc: true
---

# 过程
## 分区
对固态硬盘分区
移动或分隔分区，傲梅分区提示需要重启，在pre中处理，但是重启无效。
分配空闲分区就ok，但是在重启的时候，出现错误信息，提示 Win 10 1703版本以上不可以修改系统分区。放弃后蓝屏，100%后无反应。强制断电。再次启动时触发自动修复，正在诊断你的电脑。

Win10压缩固态硬盘，只压缩处2G。
使用机械硬盘，对其进行压缩。
傲梅分区也无法处理，使用Win10压缩卷功能。

## 启动盘制作
直接复制ISO文件中内容到U盘中。
>错误：

## Bios
bios无法进入
>win10直接安装ubuntu

## 使用easybcd
不能放在c盘
放在d盘，不能没有生成的A*文件，再次查看配置，发现指向了D盘根目录。需要指定制定iso文件的位置？
defragementation

>4752g刷bios

刷2.15 bios 提示: PhoenixUEFI Flash Tool--Please connect battery

>wsl可以ssh

>win中直接安装ubuntu

>autoneogrub.mbr

继续尝试EasyBCD
load iso from memory，fail

>4750g刷bios需要电池

https://askubuntu.com/questions/276923/how-can-i-fix-the-missing-nst-autoneogrub0-mbr-error-on-windows-8
EasyBCD doesn't work with UEFI. Refer to their FAQ.
Does EasyBCD have EFI support? No, not yet.
Refer instead to this question: Installing Ubuntu Alongside a Pre-Installed Windows with UEFI
answered Apr 3 '13 at 5:26

When I Dual booted Win 10 with Linux I just used Grub2 to manage it.

https://stackoverflow.com/questions/29809005/nst-autoneogrub0-mbr-missing
EasyBCD is not great when it comes to UEFI Systems. Read: https://neosmart.net/forums/threads/easybcd-is-deadly-dangerous-on-uefi-systems.9342/ Did you make a boot configuration restore point ? If you did, refer: https://askubuntu.com/questions/230878/dual-boot-windows-8-and-ubuntu-with-windows-8-boot-manager


>刻录ISO文件和直接复制iso内部文件的差别

没有区别。只是用词不同。一般来说，复制是指用系统自带的刻录功能进行刻录，而刻录是指用刻录软件来刻录。

用RAR解压ISO文件与用虚拟光驱来提取有区别，用RAR解压后可以保存解压后的文件，而用虚拟光驱是读取文件。


[在你的电脑上，有 5种尝试和安装Ubuntu的方法](https://www.helplib.com/Linux/article_13874)
1. 从实时USB驱动器或者光盘引导
发现Rufus
制作过程中发现启动盘不只是复制文件到U盘。
提示下载。
一个坑是制作完成后，状态是准备就绪，开始按钮可点。

多了autorun.inf、autorun.ico、syslinux.cfg、ubuntu

还是无用。

尝试增加BCD。
GRUB2
	指定驱动器
	自动定位
SysLinux

都是AutoNeoGrub*.mbr文件缺失

尝试PLoP



