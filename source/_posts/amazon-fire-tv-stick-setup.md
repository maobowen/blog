---
title: 亚马逊 Fire TV Stick 配置教程
date: 2020-12-05 20:30:00
lang: zh-CN
categories:
- 996.ICU
tags:
- Amazon
- Smart TV
---
*This article is about setting up an Amazon Fire TV Stick, and is only available in Chinese.*

今年感恩节假期因为美国疫情失控，最终临时取消了去外州旅游的计划。四天闷在阴雨连绵的西雅图感觉挺没劲的，不过好在趁着黑五购物季下单的亚马逊智能电视盒子 Fire TV Stick 和智能音箱 Echo Dot 在假期尾声送到了，于是乎稍微折腾了一番，也算是没有完全浪费掉好不容易等到的一个长假期。这篇文章记录了我对于配置 Fire TV Stick 的一些建议。

<!-- more -->

## 为什么要买 Fire TV Stick 和 Echo Dot

我现在的公寓里目前只有一台[32寸2K曲面显示器](https://www.amazon.com/dp/B07B8DXNDZ/)，并没有电视机。我之所以一直想买个电视盒子，是因为坐在床上看视频时一开始用蓝牙鼠标操作电脑感觉很不方便。虽然我后来尝试了一款叫 [<img class="not-fancy inline-app-icon" src="https://is3-ssl.mzstatic.com/image/thumb/Purple124/v4/11/c3/e5/11c3e57c-d591-3b19-04c0-4974e6d1b118/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Remote Mouse](https://www.remotemouse.net/) 的应用，但因为电脑在显示器上的分辨率很高，床又离显示器有点远，所以坐在床上时看不清楚文字和光标，操作起来还是有一点不便。而亚马逊的 Fire TV Stick 配有遥控器，加之是基于 Android 系统可定制性强，价格又比 Apple TV 亲民得多，黑五以$29.99入手一支原价$49.99的[4K版](https://www.amazon.com/dp/B079QHML21/)还是很划算的。

<img alt="亚马逊第一代 Fire TV Stick 4K" src="amazon-fire-tv-stick-setup_01.jpg" style="max-width: 800px;" />

买 Echo Dot 的理由则比较简单：因为 Fire TV Stick 默认通过电视的内置音箱播放声音，而我是把电脑显示器当电视用。众所周知，显示器内置音箱的音效一般都很差，所以我需要一台外置音箱。亚马逊的电视盒子当然要搭配自家的音箱用会比较好，而 Echo Dot 的第三代和第四代感觉功能上没什么区别，第四代体积大反而更占地方，所以以$18.99买一台原价$39.99的[第三代 Echo Dot](https://www.amazon.com/dp/B07FZ8S74R/) 就够了。

<img alt="亚马逊第三代 Echo Dot" src="amazon-fire-tv-stick-setup_02.jpg" style="max-width: 800px;" />

## 配置硬件

配置硬件的部分基本上跟着说明书一步步操作就行了。我是先收到的 Echo Dot，所以先在手机上安装 [<img class="not-fancy inline-app-icon" src="https://is1-ssl.mzstatic.com/image/thumb/Purple124/v4/8e/e3/d2/8ee3d2ff-78e5-4f66-046f-43ae2200aeac/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Amazon Alexa 应用](https://www.amazon.com/b?node=18354642011) 让音箱先工作起来。收到 Fire TV Stick 之后把它插到显示器上，再配对好遥控器，然后跟着向导设置即可。

<img alt="配置好的 Fire TV Stick" src="amazon-fire-tv-stick-setup_03.jpg" style="max-width: 800px;" />

对于在显示器上用 Fire TV Stick，这里有一点需要额外注意：设置向导里有一步是让你按 Fire TV 遥控器的音量增大、减小键检查输出音量是否发生变化，而显示器的内置音箱可能对这两个按键并没有效果，输出音量没有变化。这种情况下直接在屏幕上选 Yes 跳过即可（选 No 的话后面会让你重试很多次）。然后配置完 Fire TV Stick 之后去 Amazon Alexa 应用里添加一个声音系统 (Audio System)，把 Fire TV Stick 和 Echo Dot 或者其他蓝牙音箱组成一个家庭影院 (Home Theater)。这样的话 Fire TV Stick 就会通过音箱输出声音了，而且 Fire TV 遥控器的音量按键可以正确调节 Echo Dot 的音量。

最后推荐在手机上安装 <img class="not-fancy inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple124/v4/30/4c/f6/304cf62a-c0d0-ecec-9dbf-a19f6f9f8d61/FireTV-AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Fire TV 应用。虽然这个应用本意是用来代替实体遥控器的，看上去没有太大的用处，但它的好处是当你在电视上要输入很长一串文字时，用实体遥控器一个一个选择字母非常不方便，而用这个应用的话会方便很多。（但不得不承认，iOS 内置虚拟 Apple TV 遥控器要比 Fire TV 的这个遥控器应用好用得太多了……）

## Fire TV 装机必备应用

Fire TV 跟其他美国的智能电视盒子相比最大的优势在于，它除了可以安装来自内置应用商店 [Appstore](https://www.amazon.com/b?node=10208590011) 里的应用，也可以安装任何 Android 应用 （英文称之为 sideload）。这种高度的可定制性意味着我们可以通过安装任意 Android 应用来补全 Fire TV 很多没有自带的功能，例如翻墙回国以观看国内各大视频网站。

下面这些 Fire TV 应用我强烈推荐大家安装，其中有些可以直接在内置应用商店里下载安装，有些需要通过其他渠道获得，因此它们需要按照顺序依次安装。

需要注意的是，要从其他渠道安装应用，必须要事先在 Fire OS 的 Settings -> My Fire TV -> Developer Options 里打开 Apps from Unknown Sources 选项。具体步骤可以[点这里](https://www.aftvnews.com/how-to-enable-apps-from-unknown-sources-on-an-amazon-fire-tv-or-fire-tv-stick/)。

<img alt="打开 Apps from Unknown Sources 选项" src="https://www.aftvnews.com/wp-content/uploads/2015/08/new-interface-settings-section-developer-options-apps-from-unknown-sources-menu.jpg" style="max-width: 800px;" />

### <img class="not-fancy inline-app-icon" src="https://images-na.ssl-images-amazon.com/images/I/31Xj%2BlMLinL.png" /> Downloader

<img alt="Downloader" src="https://images-na.ssl-images-amazon.com/images/I/61Uv-UUSzOL.png" style="max-width: 800px;" />

[Downloader](https://www.aftvnews.com/downloader/) 是 Fire OS 上的下载神器，我们可以利用它下载那些没有在内置应用商店里上架的 Android 应用的安装包（`.apk`文件）以及任何其他文件。它还内置一个简易浏览器，方便用户获取下载链接。因此，配置好 Fire TV Stick 后应该第一个安装它，而且后面提到的一些应用也需要用它来下载。这款应用可以直接在内置应用商店里获得。

### <img class="not-fancy inline-app-icon" src="https://is5-ssl.mzstatic.com/image/thumb/Purple124/v4/08/4b/71/084b716c-654c-1357-41ad-664413eadfb8/AppIcon-0-1x_U007emarketing-0-7-0-0-85-220.png/230x0w.webp" /> ES文件浏览器

![ES文件浏览器](https://troypoint.com/wp-content/uploads/2018/10/es-install1.png)

[ES文件浏览器](http://www.estrongs.com/)一直都是 Android 系统上一款很不错的文件管理应用，这个 Fire OS 版本也不例外。其中一个比较强大的功能是它可以在 Fire TV Stick 上开启一个 FTP 服务器，然后我们可以通过电脑上的 [FileZilla](https://filezilla-project.org/download.php?show_all=1) 等软件很方便地往电视盒子里传输文件。这款应用也可以直接在内置应用商店里获得。

### <img class="not-fancy inline-app-icon" src="http://pic.dangbei.net/uploads/new/151121/9-151121140634C0.png" /> 当贝市场

![当贝市场](https://jt.dangbei.net/img/db/images/1.jpg)

我们可以从[当贝市场](http://www.dangbei.com/app/)里补全不少国内 Android 智能电视应用，例如 [<img class="not-fancy inline-app-icon" src="http://pic.dangbei.net/uploads/new/151230/9-15123012400KO.png" /> 奇异果TV](https://app.iqiyi.com/tv/player/) （爱奇艺TV版）、[<img class="not-fancy inline-app-icon" src="http://pic.dangbei.net/uploads/new/190620/9-1Z6201G953629.png" /> 云视听小电视](https://app.bilibili.com/) （哔哩哔哩TV版）等。当贝市场需要通过 Downloader 访问 <http://www.dangbei.com/apps/> 并点击「立即下载」获得。因为要输入一长串字母，这时之前提到的手机 Fire TV 应用就派上用场了。

### 一款可以用来翻墙回国的应用

因为地域版权限制，很多国内视频音乐类应用里的内容在境外是无法播放的。例如，B站的正版番剧在境外看不了，网易云音乐或QQ音乐的很多歌在境外也无法播放。这时我们需要一款可以用来翻墙回国的应用来「解锁」这些音视频。

对于购买了会员的用户来说，[<img class="not-fancy inline-app-icon" src="https://is5-ssl.mzstatic.com/image/thumb/Purple124/v4/be/fd/e7/befde730-b1ff-c92b-f87f-c4b8f3fa7ed2/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> 穿梭](https://www.transocks.com/)在速度和稳定性方面还是很好的。Fire TV 的内置应用商店里有穿梭的 Fire TV 版可供安装。然而跟手机版不同的是，免费用户只能试用TV版一天，过期了之后就必须购买，所以不想花钱的就可以不用考虑它了。（当然，你也可以在安装完后面推荐的一款鼠标应用后，用 Downloader 去官网下载 Android 手机版走免费线路，但这款鼠标应用有一些副作用，下文会提到。）

![穿梭TV版](https://images-na.ssl-images-amazon.com/images/I/313l2nRmAOL.jpg)

不想花钱的可以考虑 [<img class="not-fancy inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple114/v4/79/a5/5f/79a55fb2-1f7d-8fb9-e94b-c1bd346d7c94/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Malus](https://getmalus.com/)。Malus 的TV版提供免费线路，只要注册一个账号就可以用了。免费线路的体验，不论在 Fire TV 上还是在电脑或手机上，都不是很理想，但至少这是一个翻墙回国的免费选项。Malus TV版可以直接在当贝市场里下载安装，也可以用 Downloader 访问官网 <https://getmalus.com/tv> 获得。当然，Malus 也有收费的会员服务。

<img alt="Malus TV版" src="https://malus.s3cdn.net/uploads/tv_download.jpg" style="max-width: 800px;" />

### <img class="not-fancy inline-app-icon" src="http://fluxii.com/wp-content/uploads/mousetogglefiretv.png" /> Mouse Toggle for Fire TV

在介绍这款应用之前先要讲一个概念。尽管理论上 Fire TV 上可以安装所有32位的 Android 应用，但这并不意味着这些 Android 应用都能在 Fire TV 上正常工作。其背后的原因在于：大多数手机版的 Android 应用并没有对智能电视盒子和遥控器进行特别优化，遥控器上的按键很多时候在手机版应用里并不起作用（例如你怎么按遥控器正中间的OK键都无法关掉一个对话框等），一些只有竖屏模式的应用在电视或者电脑显示器上的显示效果也很奇怪。因此，有些应用才有了针对智能电视进行了特别优化的TV版，而我们一般情况下也需要在电视盒子上安装专门的TV版应用。

但有时候，一款应用并没有TV版而我们仍然想用它。例如上文提到的有人想使用穿梭 Android 手机版的免费线路，有人想安装手机版的浏览器（特别针对 Fire TV 优化过的两个浏览器的用户体验实在是太糟糕了，下文会提到）。这时候我们需要借助一款叫 [Mouse Toggle for Fire TV](http://fluxii.com/mousetoggle-firetv/) 的应用。这款应用可以在任何第三方应用中激活「鼠标」，一个类似于 Downloader 内置浏览器里的圆形光标，然后我们可以通过遥控器上方向键操控光标指针来操作这些手机版应用。

在安装 Mouse Toggle 前，首先要在 Fire OS 的 Settings -> My Fire TV -> Developer Options 里打开 ADB Debugging 选项。具体步骤可以[点这里](https://www.aftvnews.com/how-to-enable-adb-debugging-on-an-amazon-fire-tv-or-fire-tv-stick/)。

<img alt="打开 ADB Debugging 选项" src="https://www.aftvnews.com/wp-content/uploads/2014/12/new-interface-settings-section-developer-options-adb-debugging-menu.jpg" style="max-width: 800px;" />

Mouse Toggle for Fire TV 目前最新的1.11版可以用 Downloader 从这里获得：<https://www.firestickhow.com/mouse>。启动应用后，把 Enable the mouse service 打开，然后等 Status 变成 started 即可。如果屏幕上有弹出是否允许 USB 调试的话，需要勾选 Always allow from this computer 并且同意。

<img alt="Mouse Toggle for Fire TV" src="https://g8m9f6u5.stackpathcdn.com/wp-content/uploads/2018/09/mouse-toggle-on-firestick-9.jpg" style="max-width: 800px;" />

![允许 USB 调试](https://www.aftvnews.com/wp-content/uploads/2017/12/ADB-Debugging-RSA-Key-Fingerprint-800x450.jpg)

在任意一款应用中，可以使用以下按键进行操作（注意，光标在 Fire TV 的主界面中不起作用，只能在第三方应用中使用）：

- 播放/暂停键快速按两次：调出或隐藏光标；
- 方向键：移动光标；
- OK键：单击；
- 菜单键：向上滚动；
- 快进键：向下滚动。

Mouse Toggle 这款应用看上去很强大，然而其实有一个副作用：由于调出或隐藏光标需要按播放/暂停键两次，这会触发某些应用在后台播放或者暂停音频。比如说，你之前在用 Spotify 播放音乐或者用 TuneIn 收听广播电台而后来暂停并退出了应用，但按遥控器上的主屏幕键并没有令这些应用被彻底关闭——事实上，它们还在后台运行。这时你打开了手机浏览器并想调出光标。如果你按播放/暂停键两次，你可能会触发后台的 Spotify 或者 TuneIn 等继续播放。因此，我不推荐大家打开 Mouse Toggle 设置里的 Auto start the mouse service on device start-up 选项，并且仅在有需要时去启用鼠标，在用完后及时关闭。

另外，Mouse Toggle 应用存在一个风险：我们之前勾选了「总是允许 USB 调试」的选项（如果不勾选的话应用可能无法正常工作），这会令 Fire TV Stick 非常容易受到恶意程序的攻击（有兴趣的话可以读一下[这篇报道](https://www.aftvnews.com/android-malware-worm-that-mines-cryptocurrency-is-infecting-amazon-fire-tv-and-fire-tv-stick-devices/)）。因此，除非你一定要使用某些不支持遥控器的手机版应用，否则我不建议普通用户安装 Mouse Toggle，尽管它的功能还是很强大的。

### <img class="not-fancy inline-app-icon" src="http://www.airscreenapp.com/img/logo.png" /> AirScreen

用过 Apple TV 的人一定会对 AirPlay 投屏功能赞不绝口，那么对于 iPhone 用户，Fire TV 上有相似的解决方案吗？答案是有的，去内置应用商店下载这款 [AirScreen](http://www.airscreenapp.com/) 应用就行了。这款应用支持 AirPlay、Google Cast、Miracast 等多种主流投屏协议，可以满足比较基本的投屏需求。然而，和 Apple TV 开机就启动了 AirPlay 不用，在 Fire TV 上投屏前先要去这款应用里手动启动服务器，而且有时候投屏会失败，例如无法播放加密的 HLS 串流。

## Fire TV 使用心得

装完了上面那些工具类应用之后，接下来就可以根据自己的需要安装其他应用了。下面我会分享一下在不同的情景下我的一些使用心得。

### 听音乐

用 Fire TV 听歌感觉有点大材小用了，不过内置应用商店里还是有不少国外主流的音乐串流应用，例如 [<img class="not-fancy inline-app-icon" src="https://is1-ssl.mzstatic.com/image/thumb/Purple124/v4/b1/4e/1a/b14e1a6a-5bf1-87b5-196e-d23945463718/AppIcon-0-0-1x_U007emarketing-0-0-0-6-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Spotify](https://www.spotify.com/)，[<img class="not-fancy inline-app-icon" src="https://is5-ssl.mzstatic.com/image/thumb/Purple114/v4/25/64/b2/2564b267-46c3-8a71-fb84-d7cf34a7fa8f/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Pandora](https://www.pandora.com/)，[<img class="not-fancy inline-app-icon" src="https://is5-ssl.mzstatic.com/image/thumb/Purple124/v4/30/27/1e/30271e49-029e-ad4d-52ef-02569caca3b5/AppIcon-1x_U007emarketing-0-7-0-85-220.png/230x0w.webp" /> TIDAL](https://tidal.com/) 和亚马逊自家的 [<img class="not-fancy inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple114/v4/66/bd/0a/66bd0ab4-049f-78b7-bb4e-796155448c0c/AppIcon-0-0-1x_U007emarketing-0-0-0-10-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Amazon Music](https://music.amazon.com/) 等，大家可以根据自己的订阅情况各取所需。像我这种没有任何订阅的，听粤语歌用 Spotify 免费版足矣，而听日语歌就一般直接开 [<img class="not-fancy inline-app-icon" src="https://is5-ssl.mzstatic.com/image/thumb/Purple114/v4/b9/58/d8/b958d83b-f5d2-b746-df90-d0a0a244d6ad/logo_youtube_color-0-0-1x_U007emarketing-0-0-0-6-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> YouTube](https://www.youtube.com) 了。其实 Alexa 手机应用里可以绑定各个串流服务，其中甚至可以绑定 Apple Music，所以就算不开 Fire TV Stick 也直接用 Alexa 控制 Echo 设备放歌。

![Spotify](https://images-na.ssl-images-amazon.com/images/I/41lXLPU7NWL.jpg)

至于大家更喜欢用的国内音乐软件，[<img class="not-fancy inline-app-icon" src="https://is4-ssl.mzstatic.com/image/thumb/Purple124/v4/50/fe/51/50fe5166-4c16-4b30-2968-fdfcbae5e009/AppIcon-0-0-1x_U007emarketing-0-0-0-6-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> 网易云音乐](https://music.163.com/)并没有提供TV版；[<img class="not-fancy inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple114/v4/73/9b/59/739b5914-d1c0-93d4-15ea-5e9423a06b17/AppIcon-0-1x_U007emarketing-0-5-0-0-85-220.png/230x0w.webp" /> QQ音乐](https://y.qq.com/)TV版可以从当贝市场或者官网 <https://y.qq.com/download/download.html> 获取，但需要配合使用穿梭或者 Malus 使用，不是很方便。如果不存在 Spotify 加 YouTube 解决不了的歌的话感觉没必要安装它们。

### 听广播电台

这里的「广播电台」指的是传统的无线电广播，并非音乐串流平台上的音乐电台或播客。用内置应用商店里的 [<img class="not-fancy inline-app-icon" src="https://is1-ssl.mzstatic.com/image/thumb/Purple114/v4/8b/76/4d/8b764d6e-60cd-abea-b25f-12967590ac1b/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> TuneIn](https://tunein.com/radio/home/) 或者 [<img class="not-fancy inline-app-icon" src="https://is5-ssl.mzstatic.com/image/thumb/Purple114/v4/75/55/e6/7555e6d5-93b0-eeef-d92b-db201f07e24b/AppIcon-0-1x_U007emarketing-0-6-0-0-85-220.png/230x0w.webp" /> iHeartRadio](https://www.iheart.com/live/) 就可以收听很多境外电台。其中 TuneIn 的频道非常丰富，不但有 [KUOW](https://www.kuow.org/)、[KIRO](https://mynorthwest.com/category/kiro-radio/) 等几乎所有的西雅图本地频道，甚至收录了世界各地的电台，例如香港电台和香港新城电台的所有频道。iHeartRadio 则只有美国和墨西哥的电台。

<img alt="TuneIn" src="https://images-na.ssl-images-amazon.com/images/I/A14cNprEYeL.png" style="max-width: 800px;" />

TuneIn 对于国内的电台收录得不是很全，例如里面虽然有上海动感101但不能播放。想要收听国内电台的话，在 Fire TV 上我尝试了从当贝市场中安装 [<img class="not-fancy inline-app-icon" src="https://is5-ssl.mzstatic.com/image/thumb/Purple124/v4/fa/11/e1/fa11e14a-2cfe-f16e-6354-4ca308d3e331/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-85-220.png/230x0w.webp" /> 蜻蜓FM](https://www.qingting.fm/radiopage)和 [<img class="not-fancy inline-app-icon" src="https://is3-ssl.mzstatic.com/image/thumb/Purple114/v4/5c/1a/9f/5c1a9fc3-235c-6ab3-1d19-22d9688a4d42/_U559c_U9a6c_U62c9_U96c5.png/230x0w.webp" /> 喜马拉雅](https://www.ximalaya.com/)的TV版，但它们的效果都很差：蜻蜓FM完全找不到电台，喜马拉雅则只有回放，所以基本上放弃了。而且事实上，我感觉直接用小度音箱来收听动感101更方便。

### 看电视台

作为电视机最基本的功能，下面介绍一下如何在 Fire TV 上收看电视。跟听电台类似，内置的 Amazon News 就有提供几个新闻频道直播，包括全国性的 [ABC News](https://abcnews.go.com/Live) 和 [CBS News](https://www.cbsnews.com/live/) 等，以及一些本地频道，例如西雅图的 [KIRO](https://www.kiro7.com/video/live-stream/https://www.kiro7.com/video/live-stream/) 和纽约的 [WCBS](https://newyork.cbslocal.com/live/channel/wcbs-live-311/)。如果需要收看更多频道，可以去内置应用商店里下载 [<img class="not-fancy inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple114/v4/f7/63/26/f763261b-f59c-69ce-91cf-50e42ddc48d1/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Pluto TV](https://pluto.tv/live-tv)。其中新闻类别中有 [NBC News](https://www.nbc.com/live)，[CNN](https://www.cnn.com/) 以及英国的 [Sky News](https://news.sky.com/story/watch-sky-news-live-10315632)，而体育类别中则有 CBS Sports 和 FOX Sports 等。如果需要收看更多本地频道，我强烈推荐内置应用商店里的 [<img class="not-fancy inline-app-icon" src="https://is4-ssl.mzstatic.com/image/thumb/Purple124/v4/27/63/fb/2763fb02-4cc4-9a5c-42ba-1b7f899409c0/AppIcon-1x_U007emarketing-0-7-0-0-85-220.png/230x0w.webp" /> Locast](https://www.locast.org/)。Locast 虽然只在美国部分城市提供服务而且需要验证地理位置，但里面的本地数字电视频道非常全，西雅图的五大本地电视台 [KOMO](https://www.komonews.com/)，[KING](https://www.king5.com/)，KIRO，[KCTS](https://www.kcts9.org/) 和 [KCPQ](https://www.q13fox.com/) 全都有提供。 

![Amazon News](https://miro.medium.com/max/700/1*85IUbnL0VBIoLxw0jWu7Ig.png)

<img alt="Locast" src="https://images-na.ssl-images-amazon.com/images/I/71wVcFnrO5L.png" style="max-width: 800px;" />

当然，大家可能更多想看的还是国内的电视台。虽然 Fire TV 内置应用商店并没有提供中国电视台的直播应用，但当贝市场里的直播应用太多了，随便下载一款就好。我用的是HDP直播，需要从其官网上下载：<http://www.hdplive.net/>。它里面不仅收录了全国绝大部分的电视台，甚至提供了自定义源的功能方便添加境外电台电视台。感兴趣的可以参考[这个官方教程](http://www.hdpfans.com/thread-486314-1-1.html)，我也会在文末分享一些港澳地区的电视电台直播源。

<img alt="HDP直播" src="http://pic.dangbei.net/uploads/new/191118/9-19111Q31FX21.jpg" style="max-width: 800px;" />

考虑到也有人可能会选择用内置应用商店里的 [<img class="not-fancy inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple124/v4/0d/48/91/0d489179-91ab-43e2-07b9-9857a4cf1608/AppIcon-1x_U007emarketing-0-7-0-0-85-220.png/230x0w.webp" /> VLC 播放器](https://www.videolan.org/vlc/)或者自行安装 Kodi（官网下载：<https://kodi.tv/download>），而这两款应用可能需要用到`.m3u`格式的文件，这里推荐一个电视源格式转换的工具：<https://guihet.com/tvlistconvert.html>，可以快速在各种文件格式之间转换。

### 看动画

当初买 Fire TV Stick 主要是为了解决看动画的问题。首先我自己不习惯看英文字幕版动画，因此尽管内置应用商店里有 [<img class="not-fancy inline-app-icon" src="https://is2-ssl.mzstatic.com/image/thumb/Purple114/v4/f3/90/0b/f3900bbc-8415-96d2-807b-5c3462b4c1c6/AppIcon-0-0-1x_U007emarketing-0-0-0-10-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Crunchyroll](https://www.crunchyroll.com/)，[<img class="not-fancy inline-app-icon" src="https://is1-ssl.mzstatic.com/image/thumb/Purple124/v4/6d/00/f0/6d00f0ac-7092-2dab-e387-c67e40a6445b/AppIcon-0-0-1x_U007emarketing-0-0-0-10-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Funimation](https://www.funimation.com/)，[<img class="not-fancy inline-app-icon" src="https://is3-ssl.mzstatic.com/image/thumb/Purple114/v4/43/f9/2c/43f92c63-b61e-4ea3-394f-2f677e219bf6/AppIcon-0-0-1x_U007emarketing-0-0-0-10-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> HIDIVE](https://www.hidive.com/) 和 [<img class="not-fancy inline-app-icon" src="https://is3-ssl.mzstatic.com/image/thumb/Purple113/v4/42/83/57/428357a9-3b00-f1d1-2a10-477f020c9455/AppIcon-0-0-1x_U007emarketing-0-0-0-10-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> VRV](https://vrv.co/) 等一系列欧美动画网站的应用，我平时却很少用它们看番。

<img alt="Crunchyroll" src="https://images-na.ssl-images-amazon.com/images/I/B1iwbMhcFrS.png" style="max-width: 800px;" />

想看中文字幕版的话，理论上比较正确的做法应该是下载 [<img class="not-fancy inline-app-icon" src="http://pic.dangbei.net/uploads/new/190620/9-1Z6201G953629.png" /> 云视听小电视](https://app.bilibili.com/)，即哔哩哔哩TV版，然后搭配穿梭或者 Malus 使用。不过之前有提到说 Malus 免费线路速度慢，穿梭TV版收费，而且B站如今很多番剧也需要充大会员才有的看，这对穷苦的劳动人民们就不太友好了。所以实际上，我自己采用并推荐的是以下几种「政治不正确」的观看非正版番剧方法：

- 某个在海外党中大有名气的看电影电视剧的网站有提供TV版应用，可以用 Downloader 在官网下载。这应该是用户体验最好的一种看番姿势了。
- 使用下面推荐的 TV Bro 浏览器访问二刺螈们都熟悉的几个非正版网站，但总体来说操作起来还是有点麻烦。
- 安装那些网站的手机版应用然后配合 Mouse Toggle 使用，但因为没做适配和「鼠标」难用导致用户体验更差。
- 安装 Kodi，然后再安装大神写的插件（使用方式见[这里](https://github.com/zhengfan2014/xbmc-kodi-private-china-addons)，下载地址见[这里](https://afdian.net/@zhengfan2014)）。需要有一定的电脑知识，而且我个人使用下来发现B站视频的音画不同步现象比较严重。

### 上网

一般情况下我们不会经常用电视盒子上网，因为实在不是很方便。对于 Fire TV 而言，目前内置应用商店里有两个浏览器，[<img class="not-fancy inline-app-icon" src="https://is1-ssl.mzstatic.com/image/thumb/Purple114/v4/b4/3e/c9/b43ec980-510a-1965-50bc-82621b0a051c/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/230x0w.webp" /> Firefox](https://support.mozilla.org/en-US/kb/firefox-fire-tv) 和亚马逊自家的 [<img class="not-fancy inline-app-icon" src="https://images-na.ssl-images-amazon.com/images/I/51VCjQCvF0L.png" /> Amazon Silk](https://www.amazon.com/dp/B01M35MQV4)。然而不得不说，两者的体验都非常差，所以不推荐大家使用。如果一定要在二者之间选一个稍微好点的话，我会选 Amazon Silk，因为 Firefox 真的巨难用。Amazon Silk 好歹还能加几个书签、请求个桌面版网页（但很多时候并没有效），而 Firefox 的 Fire TV 版基本上可以用一无是处来形容。（Mozilla 你们不能用点心么……）之前提到过在 Fire TV 上我们还可以自行安装手机版浏览器，但因为手机版浏览器大部分没有对电视进行适配，需要配合 Mouse Toggle 使用，体验之差可想而知了。

所以这里我推荐一款开源的 TV Bro 浏览器。这款浏览器在基本上还原了手机浏览器功能的同时还对遥控器进行了适配，所以可以很方便地使用遥控器加「鼠标」的组合方式使用。虽然它并没有提供诸如「请勿跟踪」(Do Not Track) 等功能，但它可以将用户代理字符串 (user agent string) 设置成电脑版 Chrome，这样我们就可以直接访问所有网站的桌面版了，这对于访问很多动画网站非常实用（因为那些网站的手机版并没有对横屏进行优化，导致在 Fire TV 上手机版页面的渲染非常糟糕）。同时，这款浏览器还可以自定义遥控器按键的功能，比如将遥控器的菜单键设置为显示主菜单。不得不说，作为一款 Android TV 版浏览器，TV Bro 非常优秀，而且自从 [<img class="not-fancy inline-app-icon" src="https://is3-ssl.mzstatic.com/image/thumb/Purple124/v4/4e/c0/7a/4ec07ab4-8187-a33d-f1e7-f7e71b3960e6/AppIcon-1x_U007emarketing-0-7-0-85-220.png/230x0w.webp" /> Puffin](https://www.puffin.com/android-tv/puffin-tv-browser/) 需要使用 Google Play （在 Fire TV 上安装 Google 服务框架比较麻烦）并收费后，TV Bro 貌似成了目前唯一在 Fire TV 上体验比较好的浏览器。TV Bro 的安装包可以直接从项目的 GitHub 上获得：<https://github.com/truefedex/tv-bro/releases>。

![TV Bro 浏览器](https://troypoint.com/wp-content/uploads/2020/10/best-android-browser-chromecast-17.png)

### 港澳地区电视电台直播源

{% spoiler %}
```
香港电视台
港台電視31 (數碼電視31台),https://rthklive1-lh.akamaihd.net/i/rthk31_1@167495/master.m3u8
港台電視32 (數碼電視32台),https://rthklive2-lh.akamaihd.net/i/rthk32_1@168450/master.m3u8
香港開電視 (數碼電視77台),http://media.fantv.hk/m3u8/archive/channel2.m3u8
翡翠台 (數碼電視81台),http://livetv.dnsfor.me/channel.18.m3u8
無綫新聞台 (數碼電視83台),http://livetv.dnsfor.me/channel.10.m3u8
無綫財經·資訊台 (數碼電視85台),http://livetv.dnsfor.me/channel.11.m3u8
有線財經資訊台 (有線電視108台),http://livetv.dnsfor.me/channel.6.m3u8
有線新聞台 (有線電視109台),http://livetv.dnsfor.me/channel.5.m3u8
有線直播新聞台 (有線電視110台),http://teslagram.com/live/channel_110.m3u8
有線綜合娛樂台 (有線電視301台),http://livetv.dnsfor.me/channel.7.m3u8
now直播台 (now TV 331台),http://teslagram.com/live/channel_331.m3u8
now新聞台 (now TV 332台),http://teslagram.com/live/channel_332.m3u8
港台直播,https://rthkcnews-lh.akamaihd.net/i/rthknews_1@312607/master.m3u8
亞洲電視經典台,http://livetv.dnsfor.me/channel.14.m3u8
耀才財經台,http://fc_video.bsgroup.com.hk:443/webcast/bshdlive-pc/playlist.m3u8
鳳凰衛視中文台,http://live-hwcdn.utvlive.top/live/551a1a8c3aca46708fd285217be3c96e/4538203d786e4803bac20e36392cffd9.m3u8
鳳凰衛視香港台,http://live-hwcdn.utvlive.top/live/a4e8cf74196e40959485a9ef4c532d02/6286b2bbb78341cd9fa92c7b37ccc03c.m3u8
鳳凰衛視電影台,http://hdtv.haust.edu.cn/hls/fhdy.m3u8
香港衛視,https://zhibo.hkstv.tv/livestream/mutfysrq/playlist.m3u8
陽光衛視,https://stream.chinasuntv.com/680k/mid_video_index.m3u8

澳门电视台
澳視澳門 (數碼電視91台),http://live4.tdm.com.mo/ch1/ch1.live/playlist.m3u8
Canal Macau (數碼電視92台),http://live4.tdm.com.mo/ch2/ch2.live/playlist.m3u8
澳門體育 (數碼電視93台),http://live4.tdm.com.mo/ch4/sport_ch4.live/playlist.m3u8
澳門資訊 (數碼電視94台),http://live4.tdm.com.mo/ch5/info_ch5.live/playlist.m3u8
澳門綜藝 (數碼電視95台),http://live4.tdm.com.mo/ch6/hd_ch6.live/playlist.m3u8
澳門-MACAU (數碼電視96台),http://live4.tdm.com.mo/ch3/ch3.live/playlist.m3u8
立法會直播,http://live4.tdm.com.mo/tv/ch21.live/playlist.m3u8
Directo das reuniôes da Assembleia Legislativa,http://live4.tdm.com.mo/tv/ch22.live/playlist.m3u8
澳亞衛視,https://live.mastvnet.com/4rlff1m/1024/live.m3u8
澳門衛視,http://stream.mastvnet.com/MSTV/playlist.m3u8

香港电台
香港電台第一台 (FM 92.6 - 94.4),https://rthkaudio1-lh.akamaihd.net/i/radio1_1@355864/master.m3u8
香港電台第一台 (FM 92.6 - 94.4),https://rthk.hk/live1.m3u
香港電台第二台 (FM 94.8 - 96.9),https://rthkaudio2-lh.akamaihd.net/i/radio2_1@355865/master.m3u8
香港電台第二台 (FM 94.8 - 96.9),https://rthk.hk/live2.m3u
RTHK Radio 3 (AM 567),https://rthkaudio3-lh.akamaihd.net/i/radio3_1@355866/master.m3u8
RTHK Radio 3 (AM 567),https://rthk.hk/live3.m3u
RTHK Radio 4 (FM 97.6 - 98.9),https://rthkaudio4-lh.akamaihd.net/i/radio4_1@355867/master.m3u8
RTHK Radio 4 (FM 97.6 - 98.9),https://rthk.hk/live4.m3u
香港電台第五台 (AM 783),https://rthkaudio5-lh.akamaihd.net/i/radio5_1@355868/master.m3u8
香港電台第五台 (AM 783),https://rthk.hk/live5.m3u
中央人民广播电台香港之声 (AM 675),https://rthkaudio6cnr-lh.akamaihd.net/i/radio6cnr_1@575604/master.m3u8
香港電台普通話台 (AM 621),https://rthkaudio6-lh.akamaihd.net/i/radiopth_1@355869/master.m3u8
香港電台普通話台 (AM 621),https://rthk.hk/livepth.m3u
新城知訊台 (FM 99.7 - 102.1),https://metroradio-lh.akamaihd.net/i/997_h@349799/master.m3u8
新城財經台 (FM 102.4 - 106.3),https://metroradio-lh.akamaihd.net/i/104_h@349798/master.m3u8
METRO PLUS (AM 1044),https://metroradio-lh.akamaihd.net/i/1044_h@349800/master.m3u8

澳门电台
Rádio Macau (FM 98.0),http://live4.tdm.com.mo/live/rch1.live/playlist.m3u8
澳門電台 (FM 100.7),http://live4.tdm.com.mo/live/rch2.live/playlist.m3u8
```
{% endspoiler %}

这里只是简单列举一部分，请低调分享。更多境内外直播资源可参见以下网站或各大智能电视讨论区：

- 电视频道：<https://github.com/djthawks/iptv/blob/master/01>
- 国内电台频道：<https://github.com/m3u8playlist/m3u8/blob/master/radioall.json>
- 境外电台频道：<https://medium.com/@fanghua/电台直播源-db67d224c7e8>

## 结语

总体来说，亚马逊的 Fire TV Stick 智能电视盒子配合 Echo Dot 智能音箱接普通电脑显示器的使用体验还是可以的。Fire TV 内置的应用商店里的应用基本上可以满足一个普通美国人对于看电视的要求；而因其非常强的可定制性，通过安装外部 Android 应用，可以很容易将其打造成一支符合中国人习惯的电视棒。看点播、看直播、听音乐或广播、上网，甚至玩游戏都挺方便的。4K版的 Fire TV Stick 原价将近$50，与同类型的 Roku Streaming Stick 和 Google Chromecast 价格持平但功能稍许更强大，与$180的 Apple TV 4K 相比则是便宜了太多。（而且不要忘了，tvOS 是很封闭的，无法像 Fire OS 那样随意安装外部应用。）因此它在美国同类型的产品中算是比较有优势的。如果趁着黑五或者亚马逊会员日 (Prime Day) 以$30的价格入手的话甚至可以和国内的各大盒子有的一拼——当然，国内的相同价位的盒子虽然会在硬件上比 Fire TV Stick 好一些，但同时缺少了美国的那些应用。所以，如果想解脱鼠标键盘束缚的话，Fire TV Stick 还是非常推荐入手的。

## 参考资料

1. James, "How to Install Mouse Toggle on FireStick," *FireStick How*. [Online]. Available: <https://www.firestickhow.com/mouse-toggle-firestick.html>.
