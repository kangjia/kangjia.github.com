---
comments: true
date: 2011-11-21 14:31:27
layout: post
slug: host-nginx-manage-shell
title: host、nginx管理脚本
wordpress_id: 159
categories:
- tech
tags:
- nginx
- shell
---

作为苦逼程序员，开发的时候经常改host，经常改nginx config ，还要经常重启nginx。
作为一个命令控，极其受不了在不同的文件夹里来回切换。
重拾bat脚本，写了个常用的脚本来打开host、nginx_conf和启动nginx。
很简单，也没做测试，可能有bug。不过可以拿这个作为base version来丰富了。

    
    
    cls
    @echo off
    goto menu
    :menu
    cls
    echo. 1 修改host
    echo. 2 修改nginx
    echo. 3 启动nginx
    echo. 4 重启nginx
    echo. 5 关闭nginx
    echo. 请输入序号
    set /p id=
    if "%id%" == "1" goto host
    if "%id%" == "2" goto nconf
    if "%id%" == "3" goto nstart
    if "%id%" == "4" goto nreload
    if "%id%" == "5" goto nstop
    pause
    
    :host
    gvim c:windowssystem32driversetchosts
    pause
    goto menu
    
    :nconf
    gvim "D:Program Filesnginx-1.0.10confnginx.conf"
    pause
    goto menu
    
    :nstart
    d:
    cd "D:Program Filesnginx-1.0.10"
    start nginx
    pause
    goto menu
    
    :nreload
    taskkill /f /im nginx.exe >nul
    goto nstart
    
    :nstop
    taskkill /f /im nginx.exe >nul
    pause
    goto menu
    
    



