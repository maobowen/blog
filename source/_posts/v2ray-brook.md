---
title: Setting Up V2Ray and Brook Proxy Servers
date: 2020-02-25 17:00:00
lang: en
categories:
- Across the Great Wall...
tags:
- GFW
---

Last time I talked about [setting up a ShadowsocksR proxy server](../shadowsocksr). However, ShadowsocksR is not as stable as it was, but thanks to the talented people, we have the alternatives: [V2Ray](https://www.v2ray.com/) and [Brook](https://github.com/txthinking/brook).

<!-- more -->

## Server-side Setup

### Prepare a server

This part is almost the same as [that in the previous article](../shadowsocksr#prepare-a-server), but this time, I will deploy a Vultr Cloud Compute (VC2) server with Debian 10.

> Check out my [referral links](../referrals) if you want free credits for trying virtual private servers (VPS)!

Here is a reminder: I don't recommend enabling IPv6 when setting up the server, as it might cause unexpected connection issue later.

{% asset_img v2ray-brook_01.png 800 Log into the server %}

### Install V2Ray Proxy Server

Similar to deploying a ShadowsocksR proxy server, there are already plenty of one-click scripts that take care of everything about the installation for us. Here we will use [the script](https://git.io/v2ray.sh) developed by [233boy](https://github.com/233boy). First, make sure that you have `curl` installed. Then download and run the script by typing `bash <(curl -s -L https://git.io/v2ray.sh)`.

{% asset_img v2ray-brook_02.png 800 Download and run the script of V2Ray server installation %}

Enter **1** to start the installation of V2Ray proxy server.

{% asset_img v2ray-brook_03.png 800 Start installating V2Ray server %}

Use the **default setting** (i.e. hit the **Enter key**) for the transport. You can find more information about transport [here](https://www.v2ray.com/en/configuration/transport.html).

{% asset_img v2ray-brook_04.png 800 Configure V2Ray server %}

Choose a non-conflicting **port number**, and use the **default setting** for ads blocking option.

{% asset_img v2ray-brook_05.png 800 Continue configuring V2Ray server %}

Now we have the opportunity to set up a Shadowsocks proxy server at the same time. Even though Shadowsocks protocol is pretty unstable nowadays, there's no harm for us to add this "backup" option. So hit **Y** to continue setting up Shadowsocks, choose another **port number** and a **password**, and use the **default setting** for the encryption method. If everything is good, hit the **Enter key** and the script will do all the dirty work then.

{% asset_img v2ray-brook_06.png 800 Configure Shadowsocks server %}

Finally, You will see all the configuration detail as shown below.

{% asset_img v2ray-brook_07.png 800 Installation of V2Ray and Shadowsocks servers finished %}

In order to set up the V2Ray client easily, we need the VMess URL for our V2Ray proxy server. Therefore, type `v2ray url` to retrieve that URL and write it down.

{% asset_img v2ray-brook_08.png 800 Retrieve VMess URL %}

Similar to the ShadowsocksR script, we can use this V2Ray script to manage our V2Ray proxy server settings by typing `v2ray`.

{% asset_img v2ray-brook_09.png 800 V2Ray server management script %}

A useful operation here is to set up a separate proxy for Telegram. Choose **6**, enter **Y**, then pick another **port number**. If everything is good, hit the **Enter key**.

{% asset_img v2ray-brook_10.png 800 Configure MTPROTO proxy for Telegram %}

And later we can use the link below to set up the proxy for Telegram.

{% asset_img v2ray-brook_11.png 800 Configuration of MTPROTO proxy for Telegram finished %}

### Install Brook Proxy Server

We will still use [the one-click script](https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/brook.sh) developed by [Toyo](https://github.com/ToyoDAdoubi). First, make sure that you have `wget` installed. Then download and run the script by typing `wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/brook.sh && chmod +x brook.sh && bash brook.sh`.

{% asset_img v2ray-brook_12.png 800 Download and run the script of Brook server installation %}

Enter **1** to start the installation of Brook proxy server. Choose a non-conflicing **port number** and a **password**, and use the **default settings** for Brook protocol and version.

{% asset_img v2ray-brook_13.png 800 Configure Brook server %}

Finally, you will see the Brook configuration detail as shown below.

{% asset_img v2ray-brook_14.png 800 Installation of Brook server finished %}

Again, we can use this Brook script to manage our Brook proxy server settings by typing `./brook.sh`.

{% asset_img v2ray-brook_15.png 800 Brook server management script %}

Different from V2Ray, a Brook proxy seems to accept only one client at a time. Therefore, we probably want multiple users for multiple devices. To add a user, choose **7** in the management script and then choose **1**, and follow the exact same instructions above.

{% asset_img v2ray-brook_16.png 800 Add a second user to Brook server %}

You will see that there are two users now. Repeat those steps to set up additional users if necessary.

{% asset_img v2ray-brook_17.png 800 Adding a second Brook user finished %}

Last, don't forget to set firewall rules for the server!

## Client-side Setup

### Set up V2Ray Client

I would recommend the following clients:

- macOS: [V2RayX](hhttps://github.com/Cenmrev/V2RayX/releases)
  - Install with Homebrew Cask: `brew cask install v2rayx`
- Windows: [v2rayN](https://github.com/2dust/v2rayN/releases)
- iOS: [Shadowrocket](https://apps.apple.com/app/id932747118)

After launching the client, we can import the VMess URL into it.

{% asset_img v2ray-brook_18.png 500 Add a VMess server in V2RayX %}

### Set up Brook Client

Brook provides native [GUI clients](https://github.com/txthinking/brook/releases).

- macOS
  - Install with Homebrew Cask: `brew cask install brook`
- iOS: [App Store](https://apps.apple.com/app/id1216002642)

{% asset_img v2ray-brook_20.png 400 Add a Brook server %}

### Set up MTPROTO Proxy in Telegram

Just visit the link in any web browser and finish setting up in Telegram.

{% asset_img v2ray-brook_19.png 600 Set up MTPROTO proxy in Telegram %}

## References

1. 233boy, "V2Ray一键安装脚本," *GitHub*. [Online]. Available: https://github.com/233boy/v2ray/wiki/V2Ray一键安装脚本.
2. Toyo, "『原创』一个优秀的跨平台 Socks5代理软件 —— Brook 一键安装管理脚本," *逗比根据地*. [Online]. Available: https://toyodadoubi.github.io/aybh4ww5-2.html.
