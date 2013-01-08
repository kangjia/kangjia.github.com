---
comments: true
date: 2011-10-30 01:26:04
layout: post
slug: centos-add-sudo-user
title: centos增加sudo用户脚本
wordpress_id: 151
categories:
- tech
tags:
- shell
---

1、添加用户组dev:：

    
    
    groupadd dev
    



2、增加dev用户租sudo权限：
编辑soduers: vim /etc/soduers 在%wheel下面加 %dev **** 
3、shell增加用户 shell如下：

    
    
    #!/bin/bash
    useradd $1 -g dev -G root -m -p $2
    echo $1:$2|chpasswd
    pwconv
    


  

  


挺简单的，方便自己玩VPS用的。

