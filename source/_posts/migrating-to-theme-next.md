---
title: 博客启用新主题 NexT 啦
date: 2019-12-31 19:00:00
lang: zh-CN
categories:
- 996.ICU
tags:
- Hexo
---

新年快乐鸭！之前一年因为学习和找工作的关系，一直没时间更新博客。最近刚刚硕士毕业了，而距离成为社畜则还有两个月，所以赶紧趁着这段「无业游民」的悠闲时光来更新一波。

这个 [Hexo](https://hexo.io) 博客一直以来用的是 [Yelee 主题](https://github.com/MOxFIVE/hexo-theme-yelee)。我很喜欢这个主题。首先它配色很不错，有5个背景图片可以选。其次它的侧边栏可定制度很高，可以加很多社交网站链接，还有一个小菜单可以显示简单的「关于我」。不过可惜的是这个主题已经4年多没更新了，它的上游项目 [Yilia 主题](https://github.com/litten/hexo-theme-yilia)也已经2年多没更新了。虽然说 Hexo 主题不需要频繁更新，但鉴于这两个主题看上去已经停止维护了，既然决定重新开始写博客，那还是应该换一个至少还在维护中的主题。

这次我用的 [NexT 主题](https://github.com/theme-next/hexo-theme-next)也是目前最多人采用的。其实当初在建站的时候我有考虑过用这个主题，但不知道为何最后没有用。时过境迁， NexT 主题也由当初的[个人维护](https://github.com/iissnan/hexo-theme-next)变成了现在的由社区维护。其实社区维护是件好事，它可以延长一个项目的寿命，该项目不会因为作者停止维护而寿终正寝。

总体来说，配置一个新主题不是一件很麻烦的事，毕竟只需要把新主题克隆下来，在 Hexo 的配置文件 `_config.yml` 里切换到新主题，最后更改一下新主题的配置文件 `_config.yml` 就好了。不过为了兼容之前的文章以及更多的做一些自定义，我还是花了一整天的时间来配置。这里就记录一下过程中遇到的一些问题。

<!-- more -->

以下内容均基于 [Hexo v4.2.0](https://github.com/hexojs/hexo/releases/tag/4.2.0) 以及 [NexT v7.6.0](https://github.com/theme-next/hexo-theme-next/releases/tag/v7.6.0) 的 Pisces 主题。

## 修改主题配置文件

主题配置文件指的是 `themes/next/_config.yml` 。这个部分其实没有太多好说的，按照自己的喜好配置就行。需要注意的有如下几点。

### 主题注入

这部分对应的是 `custom_file_path` 项。我非常喜欢 NexT 的这种模块化设计。它可以让用户非常方便地在单独的文件里自定义排版和样式，通过注入尽可能少地更改主题本身的代码。下面提到的一些配置就需要用到这个部分。这里有一个小坑：这些自定义文件默认应该存放在博客根目录下的 `source/_data` 文件夹下，而不是 NexT 主题的文件夹 `themes/next/source/_data` 。

### 背景效果

这部分对应的是 `three` ， `canvas_nest` 和 `canvas_ribbon` 项。这些效果非常炫酷，我尤其喜欢 [canvas-nest.js](https://github.com/hustcc/canvas-nest.js) 。 然而我个人不是很建议开启这些背景效果，因为开启之后至少在我的 MacBook Pro 上风扇就疯狂作响，浏览器的 CPU 占用率很高。

## 侧边栏增加国内社交网站图标

这个版本的 NexT 主题仍然采用的是 [Font Awesome v4.7.0](https://fontawesome.com/v4.7.0/)。就算是最新的 [Font Awesome v5](https://fontawesome.com/)，当中仍然缺少很多国内的社交网站图标。这部分的优化我参考了[这篇文章](https://blog.dlzhang.com/posts/89dad1c1/)的做法，通过上面提到的主题注入来实现。

## 自定义图片样式

我之前的文章里嵌入了很多纽约地铁的颜色标志，例如<img class="not-fancy nycs-bullet" src="https://upload.wikimedia.org/wikipedia/commons/3/3f/NYCS-bull-trans-1.svg" />。之前的 Yelee 主题里文章图片默认都是内联 (inline) 显示，但切换到 NexT 主题之后，图片全部变成了块级 (block) 显示。这些小的矢量图每个图片占单独一行，显得非常丑。因此我需要给所有的颜色标志单独加 CSS 样式，例如在自定义样式文件 `/source/_data/styles.styl` 里增加：

```css
.nycs-bullet {
  display: inline;
  height: 1.4em;
  margin: 0 0 -0.3em 0 !important;
}
```

然后再把文章里所有颜色标志的 HTML 代码加上 `nycs-bullet` 这个类：

```html
<img class="not-fancy nycs-bullet" src="https://upload.wikimedia.org/wikipedia/commons/3/3f/NYCS-bull-trans-1.svg" />
```

## 部分图片禁用 fancybox

我不希望所有的图片都可以点开并在 fancybox 里显示，比如上面提到的纽约地铁颜色标志。在之前的 Yelee 主题里我也更改过相关代码，然后给不用 fancybox 的图片添加了 `not-fancy` 类。在 NexT 主题下我参考了[这篇文章](https://blog.csdn.net/cddchina/article/details/79764432)的做法。我添加的代码是：

```javascript
if ($image.hasClass('not-fancy')) {
  return;
}
```

## 部分 iframe 链接启用 fancybox

和上面相反的是，我希望给某些链接（主要是 Google 地图，点击链接以后弹出一个嵌在 fancybox 里的地图）启用 fancybox 并在点开后显示一个 iframe 。在之前的 Yelee 主题里我也更改过相关代码，然后给需要 fancybox 的 iframe 链接添加了 `fancy-iframe` 类。在 NexT 主题下我同样需要手动修改主题本身的代码 `themes/next/source/js/utils.js` 。在 `$('.fancybox').fancybox(...)` 之后添加：

```javascript
$('.fancy-iframe').fancybox({
  type: 'iframe'
});
```

虽然函数 `wrapImageWithFancyBox` 的本意是给图片添加 fancybox ，理论上来说这段代码加在这里并不是很合适，但我懒得再写一个单独的函数了。

## 启用打赏

这部分本身没什么问题，只需要在主题配置文件里启用相关项并且加上二维码的图片就可以了。但当我尝试加 PayPal 二维码的时候却发现，明明在中文语言文件里加了 PayPal 的相关翻译「贝宝」，显示出来的却还是全小写的 paypal 。通过看代码，我发现在 `themes/next/layout/_partials/post/post-reward.swig` 这个文件里我还需要把 PayPal 加到内置打赏列表：

```ejs
{%- set builtin = ['wechatpay', 'alipay', 'bitcoin', 'paypal', 'venmo'] %}
```

后来想起 PayPal 提款到银行账户还要收手续费，于是乎改成了 Venmo ，而且本来美国用 Venmo 小额转账的人就远比用 PayPal 的人多。

## 全局音乐播放器

这部分是踩坑最多的。虽然我不能保证目前的解决方法是最好的，但至少这一方法能够实现我想要的效果。

我想实现的是这样的效果：首先，我需要一个全局音乐播放器吸附在网页底部，默认是迷你模式，可以按旁边的按钮弹出播放器和播放列表。其次，我希望这个播放器可以播放我的网易云播放列表。最后，我希望在切换页面的时候不要中断播放。网上搜了一圈之后，发现还是 [APlayer](https://aplayer.js.org/) 和 [MetingJS](https://github.com/metowolf/MetingJS) 搭配最好。

首先映入我眼帘的是 [hexo-tag-aplayer 插件](https://github.com/MoePlayer/hexo-tag-aplayer)。使用插件总是最省心的，但这个插件貌似实现的是用 EJS 的语法在 Markdown 文章中插入 APlayer 播放器，并不是我想要的全局播放器。

然后我看到了[这篇文章](https://yfzhou.coding.me/2018/08/08/Hexo-Next搭建个人博客（添加网页音乐播放器功能）/)以及很多其他类似的文章。这个例子里的音乐播放器再配上 MetingJS 正是我想要的效果。但既然 NexT 主题提供了主题注入功能，我不是很想去按照文章里说的那样去修改主题原来的代码。于是我想到了可以启用 `source/_data/body-end.swig` 然后把自定义的 HTML 代码注入：

```html
<!-- Global APlayer -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.css">
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/meting/dist/Meting.min.js"></script>
<meting-js
  auto="https://music.163.com/#/playlist?id=648989969"
  list-folded="true"
  fixed="true"
  lrc-type="0">
</meting-js>
```

这样一来，播放器算是基本上可以工作了。然而一旦我切换到别的页面，播放器就会立刻重新加载，上面的这个例子里也有这个问题。但讲道理我已经打开了 [PJAX](https://github.com/theme-next/theme-next-pjax)，于是乎想到了可能是添加到 `body-end.swig` 里的代码并没有被包在 PJAX 里，后来通过查看网页源代码和 NexT 主题实现 PJAX 的代码也证实了这一想法。

之后我又发现，因为 APlayer 使用了 fixed 模式，所以理论上只要把播放器放在网页的任何部分，它都能吸附在页面底部。因此我只需要找一个被包在 PJAX 里的自定义样式文件就行了。然后我尝试了[这篇文章](https://blog.yleao.com/2018/0902/hexo上的aplayer应用.html)里提到的 `sidebar.swig` ，因为通过观察我发现侧边栏貌似并不会因为切换页面而重新加载。

但后来我又发现了一个问题：每次浏览某篇博客文章，播放器会从屏幕上消失，但音乐却还在继续播放。实际上播放器并没有消失，因为它是嵌在侧边栏里。然而浏览文章时侧边栏会切换到文章目录的界面，需要手动切回后才能调出播放器。这样的用户体验很糟糕。于是我最后决定把播放器添加到 `header.swig` 里，这样播放器不会因为切换页面而从屏幕上消失了。问题解决！

## 博客添加背景图片

这部分其实也很简单，直接参考[这篇文章](https://bufsnake.github.io/hexo-next-7-xx添加背景图片.html)操作就行了。唯一的小坑就是如果想让背景图片半透明，需要使用如下的 CSS 样式：

```css
body::after {
  background: url(https://source.unsplash.com/random/1600x900?wallpapers);
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: 50% 50%;
  content: "";
  opacity: 0.2;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: -1;   
}
```
