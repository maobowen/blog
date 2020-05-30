---
title: Setting Up Phoenix OS on Parallels Desktop for Automatically Entering Graphical Interface on Startup
date: 2020-05-25 20:00:00
lang: en
categories:
- 996.ICU
tags:
- Android
---

[Phoenix OS](http://www.phoenixos.com) is an Android x86 distribution which allows users to install Android on a PC. By using [Parallels Desktop](https://www.parallels.com) or other virtual machine software, we can run Phoenix OS seamlessly on macOS. Due to some unknown reasons, Phoenix OS does not enter the graphical interface automatically after having it installed on Parallels Desktop. Since it is pretty annoying to edit the boot option manually each time when the virtual machine is booted, this article introduces a way to automate this process by modifying the [GRUB](https://www.gnu.org/software/grub/) startup menu.

<!-- more -->

## Prerequisites

To install Phoenix OS, you need to [download the ISO image](http://www.phoenixos.com/download_x86) and [follow this official installation guide](http://www.phoenixos.com/zh_CN/help/installation/iso-Legacy). UEFI boot mode did not work for me, so ensure that you follow the link above to install the OS in legacy BIOS mode.

## Manual Way to Enter Graphical Interface

After the reboot, Phoenix OS will start the terminal session automatically if no action is taken, which is not we want.

{% asset_img parallels-phoenixos-auto-gui_01.png 500 Phoenix OS Terminal Session %}

Here is [a post](https://youyou-tech.com/2019/10/10/deepin使用笔记——VirtualB/) which introduces how to manually enter the graphical interface. In brief, hit <kbd>e</kbd> twice and append `nomodeset` (**with a leading space**) to the boot command. Then press <kbd>Enter</kbd> and <kbd>b</kbd> to boot.

{% asset_img parallels-phoenixos-auto-gui_02.png 500 Change Boot Command Manually %}

## Automatic Way to Enter Graphical Interface

What the trick above does is overriding the default boot command in GRUB boot menu. The boot menu should be stored somewhere on the disk, so the idea of automating this override process is to permanently modify the GRUB configuration by appending the `nomodeset` argument to the boot entry. A user posted [some instruction](http://bbs.phoenixstudio.org/cn/read.php?tid=2961) about how to do that, but unluckily, that instruction no longer works, as I did not find any [`menu.lst` file](https://docs.oracle.com/cd/E19253-01/817-5504/gavhe/index.html) at all by searching the entire filesystem in the Phoenix OS terminal session. It seems that GRUB is mounted to a separate mount point which is not directly accessible inside Phoenix OS.

Therefore, we need a boot CD to help us access the `menu.lst` file. One option is to use the Ubuntu-based [Boot-Repair-Disk](https://sourceforge.net/p/boot-repair-cd/home/Home/) which is designed for boot repair. You can also choose any live CD of any Linux distribution. Here I use the Boot-Repair-Disk ISO image as an example. Remember that before booting from the image, change the boot order in Parallels Desktop to put CD/DVD at the first place and load the image file to CD/DVD.

{% asset_img parallels-phoenixos-auto-gui_03.png 500 Boot From Boot-Repair-Disk %}

After some investigation, I find that the `menu.lst` file that we want to modify is under `/mnt/boot-sav/sda1/grub` path. Therefore, we can use the following commands to edit this file.

```bash
cd /mnt/boot-sav/sda1/grub
sudo nano menu.lst
```

You can use whatever editor you want as long as it comes with your boot CD. Boot-Repair-Disk has GNU nano (but not Vim). Also, remember to edit the file using root permission.

{% asset_img parallels-phoenixos-auto-gui_04.png 500 Edit GRUB Menu %}

Find the line with boot entry, and append `nomodeset` argument to it.

{% asset_img parallels-phoenixos-auto-gui_05.png 500 Edit Boot Entry in GRUB Menu %}

Finally, reboot the virtual machine from hard disk (so remember to change the boot order back in virtual machine settings). This time Phoenix OS loads the graphical interface automatically.

{% asset_img parallels-phoenixos-auto-gui_06.png 500 Boot Phoenix OS After Modifying GRUB Menu %}

{% asset_img parallels-phoenixos-auto-gui_07.png 500 Phoenix OS Graphical Interface %}

## References

1. 小柚子-新闻, "deepin使用笔记——VirtualBox 6.0虚拟机安装凤凰OS," *柚柚科技*. [Online]. Available: <https://youyou-tech.com/2019/10/10/deepin使用笔记——VirtualB/>.
2. Exception, "安装系统后无法进入图形界面的临时解决办法," *Phoenix Studio*. [Online]. Available: <http://bbs.phoenixstudio.org/cn/read.php?tid=2961>.
