---
title: 观看B站东南亚版的正确姿势
date: 2021-05-12 18:30:00
lang: zh-CN
categories:
- Moe
tags:
- Animes
---
*This article introduces some ways to watch Southeast Asia geo-locked animes on Bilibili, and is only available in Chinese.*

前几天刚好在B站投了篇[专栏](https://www.bilibili.com/read/cv11252730)，整理了一下目前B站上架的2021年4月新番的海外版权分布情况，以及介绍了如何在已经「成为泰国人」的情况下观看东南亚版权的番剧。但其中最关键的部分——如何成为泰国人——是无法写进专栏的，因此就打算在自己的博客上另写一篇文章来讲解一下。

<!-- more -->

## 背景

B站为了开拓海外市场（和[爱奇艺](https://www.iq.com/)、[腾讯](https://wetv.vip/)抢生意）最近上线了[东南亚版](https://global.bilibili.com/)，并一度[上架](https://github.com/ipcjs/bilibili-helper/issues/722)了[《日在校园》（『School Days』）](https://zh.wikipedia.org/zh-cn/School_Days)、[《缘之空》（『ヨスガノソラ』）](https://zh.wikipedia.org/zh-cn/缘之空)等各种意义上都很厉害的动画，引得一众网友争相「收藏番剧」以此来炫耀自己「在B站看片」。虽然这两部~~发人深省~~少儿不宜的动画目前下架了，但东南亚版B站目前仍然有许多在主站上永远都不可能播出的作品，比如突破表番下限、被封为「1月最强」的[《回复术士的重启人生》（『回復術士のやり直し』）](https://zh.wikipedia.org/zh-cn/回复术士的重启人生)，以及因某个前生活区阿婆主口嗨而被惨遭下架的[《无职转生》（『無職転生』）](https://zh.wikipedia.org/zh-cn/无职转生～到了异世界就拿出真本事～)等。（如果撇去那些争议情节，其实《无职转生》动画第1期观看体验很棒，原作轻小说和漫画也都十分优秀。）而又因为那个前生活区阿婆主捅出的巨大娄子，从今往后日本新番都要「先审后播」，有些4月新番的大陆版到了5月中旬还未开播，硬是开历史倒车逼老二刺螈们回到了那个靠字幕组和种子追番的时代。在这种氛围下，对于想按时追番又有能力进行壁外调查的技术宅们而言，B站东南亚和港澳台限定番剧就显得弥足珍贵了。

显然，B站也意识到了越来越多人「偷渡香港」、「沦为泰国难民」这一情况以及可能对B站造成的进一步冲击（比如B站没有下架港澳台版《无职转生》至今仍被一些人用来当作冲B站的理由），于是在地域限制的部分也是下足了功夫。最早的时候，只要知道了一部东南亚版番剧的 `season_id`，不用挂泰国梯子就可以直接通过链接 `https://bangumi.bilibili.com/anime/${season_id}` 跳转到主站对应的番剧页面 `https://www.bilibili.com/bangumi/media/${media_id}/` 并对番剧进行收藏；如今这一跳转已经完全失效（即东南亚版权番剧完全与主站隔离）。再比如以前可以在主站不挂港澳台梯子的情况下搜索到仅限港澳台观看的动画，现在也不行了。博主甚至有理由担心，有朝一日如果不挂梯子，主站的[番剧索引页](https://www.bilibili.com/anime/index/)里也会看不到港澳台版权的番剧。

## 如何获取东南亚国家的梯子

如果你身在大陆，那么你只能去购买一个有泰国、新加坡等东南亚国家节点的机场。下面提到的免费VPN，虽然博主自己没有尝试过在国内能不能连，但稍微想一下的话也知道应该是不可能的。至于机场推荐……因为博主现在人在国外，没有用机场的需求，所以并不清楚相关行情。

如果你身在境外，那么有下面至少2种方法可以连到一个泰国的免费VPN。不过免费VPN的速度一般都会比较慢，安全风险也需要你自行评估。

### <img class="not-fancy text-image inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple124/v4/ef/90/54/ef905435-be80-7303-dd66-4510098a2de6/AppIcon-0-0-1x_U007emarketing-0-0-0-10-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Urban VPN

[Urban VPN](https://www.urban-vpn.com/) 的浏览器插件和手机客户端都有提供免费泰国VPN。对于电脑端，安装相应浏览器的插件即可，不必安装客户端。

<img alt="Urban VPN iOS 客户端" src="watch-bilibili-se-asia-version_01.png" style="max-width: 300px; width: 100%;" />

### <img class="not-fancy text-image inline-app-icon" src="https://is4-ssl.mzstatic.com/image/thumb/Purple124/v4/90/6d/37/906d37c4-fc24-2b34-a37d-ec978cd4f3c5/AppIcon-1x_U007emarketing-0-7-0-0-85-220.png/230x0w.webp" /> OpenVPN

[OpenVPN](https://openvpn.net/) 确切地说是一种开源虚拟专用网络协议，虽然有提供客户端，但服务器还是需要自己找的。这里推荐两个提供免费泰国 OpenVPN 服务器的地方：

- [VPN Gate](https://www.vpngate.net/) 上偶尔可以刷到新马泰的服务器，但实效性和可用性都比较差。Mac 用户下载了`.ovpn`配置文件后导入电脑客户端、或者 AirDrop 给 iOS 设备即可。Windows 用户可以直接下载它的 [SoftEther VPN 客户端](https://www.softether.org/5-download)。
- [<img class="not-fancy text-image inline-app-icon" src="https://is3-ssl.mzstatic.com/image/thumb/Purple124/v4/8d/62/7e/8d627eaf-7f79-1b76-d301-1e7a0bac2cd6/AppIcon-1x_U007emarketing-0-10-0-0-85-220.png/230x0w.webp" /> OpenVPN Profile Spider](http://sowhatstory.com/) 不定期更新公用 OpenVPN 服务器，可以使用内置的导出功能直接把配置文件导出至手机客户端、或者 AirDrop 给 Mac。下载地址：[<img class="not-fancy text-image" src="https://developer.apple.com/app-store/marketing/guidelines/images/badge-download-on-the-app-store.svg" />](https://apps.apple.com/us/app/id928941628)、[<img class="not-fancy text-image" src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg" />](https://play.google.com/store/apps/details?id=com.ovpnspider)、[Android 安装包](https://apkpure.com/best-vpn-proxy-ovpnspider/com.ovpnspider)。

<img alt="OpenVPN Profile Spider" src="watch-bilibili-se-asia-version_02.png" style="max-width: 300px; width: 100%;" />

客户端可以在这些地方下载：

- iOS 上使用官方的 <img class="not-fancy text-image inline-app-icon" src="https://is4-ssl.mzstatic.com/image/thumb/Purple124/v4/90/6d/37/906d37c4-fc24-2b34-a37d-ec978cd4f3c5/AppIcon-1x_U007emarketing-0-7-0-0-85-220.png/230x0w.webp" /> OpenVPN Connect 即可：[<img class="not-fancy text-image" src="https://developer.apple.com/app-store/marketing/guidelines/images/badge-download-on-the-app-store.svg" />](https://apps.apple.com/us/app/id590379981)。
- macOS 上也是直接使用官方的即可：[官网下载](https://openvpn.net/client-connect-vpn-for-mac-os/)或 `brew install --cask openvpn-connect`。
- Android 上的 <img class="not-fancy text-image inline-app-icon" src="https://images-na.ssl-images-amazon.com/images/I/51KdIZ8WLDL.png" /> OpenVPN for Android 更好用：[<img class="not-fancy text-image" src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg" />](https://play.google.com/store/apps/details?id=de.blinkt.openvpn)、[Android 安装包](https://apkpure.com/openvpn-for-android/de.blinkt.openvpn)。

## 如何观看仅限东南亚国家的番剧

有了东南亚国家的VPN后，播放东南亚限定的番剧就相对比较容易了。博主的[B站专栏](https://www.bilibili.com/read/cv11252730)已经给出了几种方案，有兴趣的可以去那里阅读。下面仅对那些方案做一点补充，并提供另一个不能写进专栏里的方案。

### 使用梯子和东南亚版手机应用

东南亚版的手机应用 <img class="not-fancy text-image inline-app-icon" src="https://is1-ssl.mzstatic.com/image/thumb/Purple125/v4/d3/f0/f9/d3f0f9bf-b288-25c2-5183-451420ee28e5/AppIcon-inter-0-0-1x_U007emarketing-0-0-0-4-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> 可以在这里下载：

- iOS：[<img class="not-fancy text-image" src="https://developer.apple.com/app-store/marketing/guidelines/images/badge-download-on-the-app-store.svg" />](https://apps.apple.com/sg/app/id1548857482) 需要注意的是，这款应用仅在新加坡、大马、泰国、菲律宾、越南等部分东南亚国家的 App Store 中可下载，因此需要注册一个当地的 App Store 账号。这款应用曾经在 [<img class="not-fancy text-image inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple124/v4/1c/aa/0f/1caa0f40-c57c-28b5-c4d2-df6528d9f9f1/AppIcon-1x_U007emarketing-0-7-0-85-220.png/230x0w.webp" /> TestFlight](https://apps.apple.com/app/testflight/id899247664) 上发布过[测试版](https://testflight.apple.com/join/8C3rfvbj)，不过现在已经不能用了。
- Android：[<img class="not-fancy text-image" src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg" />](https://play.google.com/store/apps/details?id=com.bstar.intl) 锁区情况暂不清楚，但可以用 [<img class="not-fancy text-image inline-app-icon" src="https://apkghost.com/wp-content/uploads/2020/04/apkpure-icon-150x150.png" /> APKPure](https://apkpure.com/apkpure-app.html) 等工具绕过 Google Play 直接下载安装`.xapk`文件。

这款应用除了功能比网页版全之外（可以浏览、搜索番剧等），还有一个好处就是可以获取 `season_id` 和 `episode_id`。这两个参数在后面的几种方案里是需要用到的。具体的方法是：选定一部动画的某一话播放，在播放界面点「Share」按钮，再点「Copy link」，就能在剪贴板里得到类似这么一个链接：

```
https://m.global.bilibili.com/play/36938/377723?s_locale=en_US&from=copy_link&share_medium=iphone
```

其中`36938`为当前番剧的 `season_id`，`377723`为当前话的 `episode_id`。

<img alt="希露菲真是太可爱了" src="watch-bilibili-se-asia-version_03.png" style="max-width: 300px; width: 100%;" />

### 使用梯子和东南亚版电脑端网页

有了 `season_id` 或者 `episode_id` 后，如果想在电脑上看的话，在挂了梯子的情况下可以直接前往东南亚版电脑端的播放页面：

```
https://global.bilibili.com/play/ss36938
https://global.bilibili.com/play/ep377723
```

<img alt="夏海小时候明明这么可爱" src="watch-bilibili-se-asia-version_04.png" style="max-width: 800px; width: 100%;" />

不过比较神奇的是，几部尺度比较大的番剧在网页版上无法观看，用手机应用却能看。博主还没有仔细研究过东南亚API的返回值，不太清楚为什么会这样。

### 使用油猴脚本和公共解析服务器

如果觉得梯子速度慢不想一直挂着，或者因为身处大陆找东南亚节点有难度，但又有 `season_id` 的情况下，还有另一种看番的方法。

[「解除B站区域限制」](https://greasyfork.org/zh-CN/scripts/25718)这个脚本想必是很多留学党在B站上追番的必备工具之一。它目前支持直接在主站的播放页面 `https://www.bilibili.com/bangumi/play/ss${season_id}` 中播放东南亚版番剧，但由于 [BiliPlus 的倒下](https://www.biliplus.com/tmp_home/end_of_service.htm)，现需要用户使用自己的解析服务器。不过好在[这里](https://github.com/ipcjs/bilibili-helper/blob/user.js/packages/unblock-area-limit/README.md)和[这里](https://github.com/yujincheng08/BiliRoaming/wiki/公共解析服务器)列出了一些网友提供的公共解析服务器。按照[教程](https://github.com/ipcjs/bilibili-helper/blob/user.js/packages/unblock-area-limit/README.md)配置好解析服务器后，就可以直接用脚本在主站上~~开车~~看番：

```
https://www.bilibili.com/bangumi/play/ss36938
```

<img alt="名场面" src="watch-bilibili-se-asia-version_05.png" style="max-width: 800px; width: 100%;" />

对于既不在大陆又不在东南亚地区的人，这样看东南亚版番剧的效果还是不错的，因为脚本的工作原理是替换播放源，而[海外版（东南亚版和港澳台版）的播放源是通过 Akamai CDN 加速的](https://www.bilibili.com/read/cv3118508/)，像是在美国的话连接速度是很理想的。

## 彩蛋

JavaScript 脚本叫金坷垃……

<img alt="本站由金坷垃强力驱动" src="watch-bilibili-se-asia-version_06.png" style="max-width: 800px; width: 100%;" />

还有，我要下车，快放我下车！

<img alt="3个月从$160跌到$90也是厉害🙄️" src="watch-bilibili-se-asia-version_07.png" style="max-width: 800px; width: 100%;" />

## 参考资料

1. 米柚子, "关于泰国番剧研究," *GitHub*. [Online]. Available: <https://github.com/ipcjs/bilibili-helper/issues/722>.
2. 社会易姐QwQ, "哔哩哔哩-API收集整理," *GitHub*. [Online]. Available: <https://github.com/SocialSisterYi/bilibili-API-collect>.
