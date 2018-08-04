---
title: Setting Up a ShadowsocksR Proxy Server
date: 2018-06-04 15:00:00
lang: en
tags:
---

Follow this tutorial to start setting up a ShadowsocksR proxy server and enjoying freedom outside the wall!

<!-- more -->

## Server-side Setup

### Prepare a server

I would recommend [DigitalOcean](https://m.do.co/c/881f697ed35a) and [Vultr](https://www.vultr.com/?ref=7436070), both of which offer various plans for [virtual private servers (VPS)](https://en.wikipedia.org/wiki/Virtual_private_server). DigitalOcean provides [\$100 credits](https://try.digitalocean.com/performance/?refcode=881f697ed35a&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=CopyPaste) for new users, while Vultr provides [\$25 credits](https://www.vultr.com/promo25b?ref=7436070) for new users. Students with a valid .edu email address can sign up for [GitHub Student Developer Pack](https://education.github.com/pack) and get an extra \$50 credits on DigitalOcean. [Google Cloud](https://cloud.google.com/free/) and [Microsoft Azure](https://azure.microsoft.com/en-us/free/), at the same time, also provide free credits for trial, but they can exhaust faster. These free credits usually last for only one year, so you should take full advantage of them before they expire. If you have access to a dedicated server, keep in mind that you should have full access to it.

I will deploy a Vultr Cloud Compute (VC2) server with Ubuntu 18.04 in this tutorial.

{% asset_img shadowsocksr_01.png 500 Log into the server %}

### Install ShadowsocksR Proxy Server

In this tutorial, we will use [a script](https://github.com/ToyoDAdoubi/doubi/blob/master/ssrmu.sh) developed by [@Toyo](https://github.com/ToyoDAdoubi) to help us install the proxy server. This script installs and runs the proxy server in the MudbJSON mode so that the we can manage each user of the proxy server separately. For those who are interested in the technical details of this script, please refer to [『原创』ShadowsocksR MudbJSON模式多用户一键脚本 支持流量限制等](https://doub.io/ss-jc60/#脚本版本) (Chinese).

Thanks to the script, the installation can be extremely easy. First, download and run the script.

```bash
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssrmu.sh && chmod +x ssrmu.sh && ./ssrmu.sh
```

{% asset_img shadowsocksr_02.png 500 Download and run the script %}

Enter **1** to start the installation of ShadowsocksR proxy server.

{% asset_img shadowsocksr_03.png 500 Start installation %}

First, hit the **Enter key** to let the script automatically detect the IP address of the server. Then enter **user name**, **port number** and **password** for the first user.

> The username and password should only contain ASCII characters. The port entered here should not have conflict with the ports which the server is using or the server system reserves.

{% asset_img shadowsocksr_04.png 500 Configure the first user %}

For the encryption method, select **"none"** (i.e. enter **1**) since I will use "auth_chain_a" protocol later.

{% asset_img shadowsocksr_05.png 500 Select the encryption method %}

Now select **"auth_chain_a"** protocol (i.e. enter **5**) because it is safer.

> For more information about "auth_chain_a" protocol, please refer to [协议auth_chain_a是啥](https://breakwa11.blogspot.com/2017/05/auth-chain-a.html) (Chinese) or https://github.com/shadowsocksr-backup/shadowsocks-rss/blob/master/doc/auth_chain_a.md (English). You might also use "auth_chain_b" protocol, but it has not been widely supported on the iOS devices yet.

{% asset_img shadowsocksr_06.png 500 Select the protocol %}

Use the **default setting** for obfuscation (i.e. enter **5**) with no compatibility with Shadowsocks (i.e. enter **n**). Original Shadowsocks proxy is no longer safe, so it is not necessary to make the server compatible with Shadowsocks.

> For more technical information about encryption method, protocol and obfuscation in ShadowsocksR, please refer to [ShadowsocksR 协议插件文档](https://github.com/iMeiji/shadowsocks_install/wiki/ShadowsocksR-协议插件文档) (Chinese).

{% asset_img shadowsocksr_07.png 500 Select the obfuscation %}

Use the **default settings** for all remaining parameters unless you want to limit the device number, the network speed, the traffic and/or the ports of the current user.

{% asset_img shadowsocksr_08.png 500 Configure the first user %}

Finally, the script shows that the proxy server is installed successfully, and the first user is configured. Write down the ShadowsocksR URL starting with `ssr://` or the QR code URL so that we can add this configuration to the clients later.

{% asset_img shadowsocksr_09.png 500 Installation finished %}

If you want to add another user, just run the script again by `./ssrmu.sh`, choose **7** and follow the exact same instruction.

In theory, we should boost our proxy server's TCP connection. The good news is that Ubuntu 18.04 enables [Google BBR](https://ai.google/research/pubs/pub45646) by default, so we do not need to take any further action. If you use other versions or systems and need to enable it manually, please follow this tutorial: [Centos/Ubuntu/Debian BBR加速一键安装包](https://www.91yun.co/archives/5174) (Chinese).

> Debian 9 users can use the following commands to enable Google BBR:
> ```bash
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p
```
> For more information, please check out this post: [Debian 9快速开启Google BBR的方法，实现高效单边加速](https://www.moerats.com/archives/297/).

And don't forget to set firewall rules for the server! [DigitalOcean](https://www.digitalocean.com/community/tutorials/an-introduction-to-digitalocean-cloud-firewalls?refcode=881f697ed35a&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=CopyPaste) and [Vultr](https://www.vultr.com/docs/vultr-firewall?ref=7436070) provide graphical interface inside their consoles so that users can set up firewalls in clicks.

## Client-side Setup

I would recommend the following client-side applications:

- macOS: [ShadowsocksX-NG](https://github.com/qinyuhang/ShadowsocksX-NG-R/releases)
- Linux: [electron-ssr](https://github.com/erguotou520/electron-ssr/releases)
- Windows: [ShadowsocksR C#](https://github.com/shadowsocksrr/shadowsocksr-csharp/releases)
- iOS: [Potatso Lite](https://itunes.apple.com/app/id1239860606)
- Android: [ShadowsocksR for Android](https://github.com/shadowsocksrr/shadowsocksr-android/releases)

## Reference

1. Toyo, "『原创』ShadowsocksR MudbJSON模式多用户一键脚本 支持流量限制等," *逗比根据地*. [Online]. Available: https://doub.io/ss-jc60/.

