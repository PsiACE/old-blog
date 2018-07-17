---
layout: post
title: 尝试使用 Jekyll 与 GitHub Pages
excerpt: 本文章介绍一些关于 Jekyll 与 GitHub Pages 的内容，为了简化流程仅仅介绍如何快速开始以及在已有主题之上进行个性化定制。
categories: [沸点分享记录]
tags: [Jekyll, GitHub Pages, 静态站点生成器]
creativecommons: true
comments: true
image:
  feature: https://psiace.me/src/FeiDianShare/Jekyll.png
  credit: Jekyll（Page Screenshots）
  creditlink: https://jekyllrb.com
---

*本文将帮助你快速入门，为了避免在介绍上花费过多时间，部分内容请感兴趣的同学自己查看官方网站和文档。*

[Jekyll](https://jekyllrb.com) 是一个优秀的静态站点生成器，[GitHub Pages](https://pages.github.com) 是 **GitHub** 提供的静态页面托管服务。使用这些，我们可以轻松地为项目/组织构建网站，也可以发布自己的博客和简历。

同时使用 Jekyll 和 Github Pages 的一个最大的好处是你可以只关注内容，这是由于有很多优秀的设计师和开发人员为 Jekyll 制作了大量的美观实用的主题，而 GitHUb 为我们节约了购置服务器的经费。唯一的限制可能仅仅是我们需要一些第三方服务来提供诸如评论和在线表单这样的功能。

本文会介绍以下几个方面的内容：
* 本地部署 Jekyll/GitHub Pages 环境
* 启用 GitHub Pages 的用户页面服务
* 使用优秀的 Jekyll Theme
* Jekyll Theme 的组织结构
* 一些第三方服务和个性化配置

好吧，让我们现在就开始，玩的开心～

### 本地部署 Jekyll/GitHub Pages 环境

首先我们需要一台联网的计算机，当然，如果没有也不用担心，我会考虑在后面添加如何使用手机来完成这项工作。

首先，你需要安装 Ruby 语言环境，这里提供 Fedora 系统上的命令行安装方法

`sudo dnf install ruby ruby-devel`

如果你使用的是 Ubuntu 系统，只需要把命令换成 

`sudo apt-get install ruby ruby-dev`

至于 [Y/N] 我们当然是选择 Y :)

如果你在使用 Windows 或是其它操作系统，请参考[这里](https://www.ruby-lang.org)，链接指向了 Ruby 的官方网站，你可以很轻易得到安装办法。

接下来，我们需要依次执行下面图示的命令：

![Install & Test](https://psiace.me/src/FeiDianShare/carbon-install-test.png)

不使用 `gem install bundler jekyll` 的原因只是我们想要构建一个与 Github Pages 完全相同的环境。

在浏览器中输入它提供的地址（也许是 `http://localhost:4000` 或是 `http://127.0.0.1:4000/`），你就可以看到一个官方提供的模板。

类似下图：

![Test Page](https://psiace.me/src/FeiDianShare/test-page.png)

如果你喜欢它，可以直接在这个上开始工作，打开文件夹，在 `_post` 目录下以 `yyyy-mm-dd-title.md` 按示例新建文件，编辑内容，然后就可以在页面上看到更改了，稍后我会额外介绍这些内容。


### 启用 GitHub Pages 的用户页面服务

如果你还没有 [GitHub](https://github.com) 的账号，我强烈推荐你注册一个，因为这是世界上最为活跃的~~同性~~交友社区之一 :) 只要访问主页，你就可以找到入口。

我强烈建议你参考 GitHub 的官方文档，它非常详细地介绍了所有你可能想要了解的内容。当然，你需要一点阅读英文文档的能力，至少要能够使用翻译。

好了，现在你已经有了 GitHub 的账号，通常情况下，我会建议你创建一个名为 `yourusername.github.io` 的存储库（请容许它使用 README 文档对存储库进行初始化，特别是当你打算试验而没有准备好内容），这样你就可以获得一个由 GitHub 友情提供的子域名，所有在主分支（`master`）的符合要求的内容都将被重构并发布，通常情况下，你可以在浏览器访问 `https://yourusername.github.io`，然后看到 `README.md` 被转化后的内容。

如果它没有正常显示或者你想在其它存储库启用 GitHub Pages，请打开存储库的 `Settings` 然后根据提示操作。如果你觉得页面光秃秃，可以通过 `Choose a theme` 来选择一个官方主题，但这不是必要的，因为我们接下来会介绍一些关于使用优秀的 Jekyll 主题和进一步定制的内容。

### 使用优秀的 Jekyll Theme

造轮子是一件有意思的工作，但它往往需要花费大量的时间，而且一个好的想法可能需要经过大量的调试才能正常工作，如果你不满足于 Jekyll 的几个默认主题，那么我建议你试着使用一些优秀的 Jekyll 主题，它们往往实现了以下功能：

* 响应式布局
* 良好的文件结构
* 标签云/文章分类
* 优化的 SEO 设置
* 第三方评论/统计插件支持

从优秀的 Jekyll 主题开始可以让你更专注于文章本身，而不是看上去数目众多的 CSS 代码 :)

这里我特别推荐三个主题：

* **[Huxblog-Boilerplate](https://github.com/Huxpro/huxblog-boilerplate)**，by [@Huxpro](https://github.com/Huxpro/)，Apache License v2.0

![Huxblog](https://psiace.me/src/FeiDianShare/Huxblog.png)

* **[Jekyll NexT](https://github.com/Simpleyyt/jekyll-theme-next)**，by [@Simpleyyt](https://github.com/Simpleyyt/)

![NexT](https://psiace.me/src/FeiDianShare/NexT.png)

* **[Leonids](https://github.com/renyuanz/leonids)**，by [@renyuanz](https://github.com/renyuanz/)

![Leonids](https://psiace.me/src/FeiDianShare/leonids.png)

如果你想

（未完待续...）
