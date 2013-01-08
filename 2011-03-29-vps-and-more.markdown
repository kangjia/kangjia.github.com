---
comments: true
date: 2011-03-29 22:44:11
layout: post
slug: vps-and-more
title: VPS and more
wordpress_id: 122
categories:
- tech
tags:
- linux
---

**VPS-爪控**




博客放免费空间，免不了被墙的命，终于等到了VPS有货，和朋友一起拼了一个。然后就兴致冲冲装系统，加用户，分权限，装ftp。在这个过程中重复的shell命令，突然觉着这种手动控不是我的风格阿～～～仰天长啸




哪里有压迫，哪里就有google。搜了一下vps的面板，发现免费滴没几个。选了kloxo，继续gg教程。差不多弄明白后才发现vpsyou提供了集成kloxo的OS。冏是一种习惯!- -。快速重装后，生活开始美好了。




**VPS-使用**




kloxo下把DNS模板填写后就开始分用户，为了以后方便，都选上了ssh。不过我在centos下木有找到sudoers文件，也没加上sudo权限。不管了，用户添加好后谁想开什么ftp，做什么站就随便了。kloxo需要apache,内存继续悲剧。期间想试试lnmp.org提供的一键包，不过木有好的人机交互就先放弃了。到这里，VPS可以提供的WWW、FTP、MAIL、MYSQL基础服务都有了，




**VPS-VPN**




VPS只做站，岂不是太对不起RMB了，想想自己也木有什么靠谱的VPN，又开始了搭梯子之旅。centos5.5下有人作了l2tp一键包，执行后就等着就是了。悲剧也进入到了高潮，我的ubuntu小本没找到l2tp连上的方式。算了，改天再去搭个openvpn的吧，另外有达人做了iptable，可以访问天朝的站不走VPN，有兴趣的童鞋可以GG一下，在googlecode开源了。BTW：买个VPS然后专门作VPN服务器去卖应该还能赚钱。白天用办公的电脑跑了一下VPN，梯子速度很给力哈。唉，还是花钱的好！




**VPS-blog**




kloxo下把站点配置好后，开始搬家之旅。centos都不带ftp客户端，不过想想可怜的内存，忍了，yum装上后，ftp到被墙的blog，wget回来zip包。然后翻墙去倒数据。改域名服务商的指向，一切很顺利的完成了搬家。^_^，终于不怕被墙了。




**VPS and more**




下午和老袁聊了一会儿，他对云貌似很感兴趣。听他讲也要转到SPD了，也不知道电信这不差钱的主会不会也使用虚拟化，也把主机作成多个VPS,充分利用下主机。不过我倒是觉着原来的BOSS用weblogic作web服务器，真是太奢侈也太浪费了。原来作BOSS作分层，还是分的不彻底。前端放个nginx，后面跟weblogic作业务容器效果应该也不错。最近也要多看看nginx，可以把这个VPS充分利用起来，试试能起几个应用。




**VPS TODO**





	
  * 对kloxo调优，现在kloxo起一天基本就200M内存+了，研究下哪些服务可以关掉

	
  * 本地ubuntu折腾一下lnmp

	
  * 记得写blog



