---
comments: true
date: 2011-07-09 23:37:38
layout: post
slug: some-bug-in-window7-install-ubuntu
title: 坑爹的window7自带分区工具
wordpress_id: 139
categories:
- tech
tags:
- linux
- ubuntu
---

作为一个轻度命令行控，把win7下安装cygwin已经不能让我完全满足了。反正现在硬盘也大，做个硬盘双系统成了必然选择。




硬盘安装ubuntu的两种方法：




1、wubi。




2、修改启动项，利用grup4dos或者easybcd安装。




对于2.网上有详尽的教程。比如：




http://letgoof.me/2011/install-ubuntu-11-04-from-harddisk-under-windows7/




好了，说重点：一般在使用window的时候，硬盘已经分区完毕了，这个时候只能从某个逻辑分区找补出来一些空间。




在win7下，恐怕很多童鞋会喜欢使用win7自带的磁盘工具进行压缩分区，但是，这里有个问题。如果是通过磁盘压缩后，




会坑爹的出现分区表错误。尤其是想使用压缩后的空间进行安装ubuntu。无论是wubi还是双系统。都会出现挂载错误问题。




1、wubi会报找不到根目录。




2、硬盘安装会出现挂载问题，找不到你的分区。







在linux下使用 sudo fdisk -lu，就会发现使用win7自带的分区工具压缩出来的分区Blocks竟然木有变？木有变！尼码有木有，有木有这么坑爹的啊！




**遇到以上问题的童鞋请注意：使用靠谱的分区工具进行分区空间调整吧。  **




比如harddisk gen2010，或者PQ之类的。



