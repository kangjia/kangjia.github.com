---
comments: true
date: 2011-01-31 00:35:14
layout: post
slug: after-setup-ubuntu
title: 安装ubuntu之后……碎碎念版
wordpress_id: 86
categories:
- tech
tags:
- linux
- ubuntu
---

为了让自己是使用linux而不是装linux，所以把自己的硬盘格掉OS切换到ubuntu下了，并准备长期坚持单OS。作为ubuntu初哥，也将点滴记录，探讨并分享使用ubuntu作为桌面系统的可用性。当然，讨论背景是轻度游戏玩家，轻度唯*系统论者，轻度自由软件和版权捍卫者。

按照普通作系统步骤，安装好系统后就是装驱动了。安装的系统为ubuntu 10.10，物理主机是tp x200，木有配置什么，除了蓝色浮点键盘不能使用，其他一切正常。蓝色浮点相当于鼠标中键，作为一个键盘控，没有中间作滚轮，是一件很纠结的事情，在google大神帮助下，安装Pointing devices，然后点击系统-首选项-Pointing devices-选中使用滚轮模拟-键值设置2-启用垂直滚动。然后就可以了。

刚才说到安装Pointing devices，再说一下ubuntu怎么安装软件及安装哪些软件。ubuntu是通过apt-get方式安装软件的，也有GUI（软件中心），当然，也要配置源，突然觉着ubuntu安装软件特别像maven，通过配置依赖关系来下载。顺便吐槽一下linux各个发行版的乱七八糟的软件环境。当然，win作为商业软件，构建生态链也是他可持续发展的因素。好了，如果想知道怎么装软件，推荐[http://forum.ubuntu.org.cn/viewforum.php?f=120](http://forum.ubuntu.org.cn/viewforum.php?f=120)学。

还是说一下我的soft list吧。

浏览器：chrome

mail：我用chrome的插件，不过预装了Evolution

下载：wget，amule。

截屏工具：shutter(真木有QQ的ctrl+alt+a好用哇)

ftp：Filezilla（win下也有，很好用的说）

为啥木有介绍office和QQ捏？

因为下面说的是vmware，可以安装virtualbox，不过使用virtualbox我遇到了内置摄像头启动不起来的问题。virtualbox如果使用USB设备，请参考[http://forum.ubuntu.org.cn/viewtopic.php?f=65&t=151221](http://forum.ubuntu.org.cn/viewtopic.php?f=65&t=151221)

虚拟机下安装个xp，然后安装office和tm。已经足够搭起来我的平时使用了。如果不用office，或者使用OOo之类的朋友及领导很多，也可以使用webQQ搞定了。别叨叨写这一段，我们使用电脑是为了生活，不是为了显摆滴。

当然，除了虚拟机也可以使用wine，还是使用apt-get安装吧，官方已经1.3+了。安装好后至少你的win下的绿色软件都可以使用了。如果需要安装什么.dll或者软件包，使用winetricks安装即可。悲催的是我竟然用不了deepin-wine的几个软件。好吧，毛爷爷讲：自己动手，丰衣足食。

除了通过虚拟机或者wine跑软件，其他ubuntu自带软件基本都满足我的需求了。这个时候需要介绍的就是面子工程了。

list：

ubuntu tweak

awn

compiz

第一个可以设置compiz，启动3D效果，恩那，比acer要cool多了，第二个可以设置一个如同mac的启动栏。

今天发现了一个好玩的软件，叫做ejecter。可以作为USB设备和外置设备的指示器小程。

再推荐个好玩的站：[http://wowubuntu.com](http://wowubuntu.com/)
